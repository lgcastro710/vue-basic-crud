<template>
  <div class="container">
    <div class="row pt-3">
      <h3>Mi lista de pasatiempos</h3>
      <Form :agregar="agregar" class=""></Form>
      <List :lista="lista" :eliminar="eliminar" class=""></List>
    </div>
  </div>
</template>

<script>
import Form from "./Form";
import List from "./List";
import firebase from "../../firebase";

export default {
  name: "Container",

  components: {
    Form,
    List,
  },
  data() {
    return {
      lista: [],
    };
  },

  methods: {
    agregar: function (clave, producto, precio, descripcion) {
      if (
        clave === "" ||
        producto === "" ||
        precio === "" ||
        descripcion === ""
      ) {
        return false;
      }
      var item = {
        clave: clave,
        producto: producto,
        precio: precio,
        descripcion: descripcion,
      };
      // app.lista.push(item);
      firebase
        .database()
        .ref("vue-store/" + clave)
        .set(item);
    },
    eliminar: function (clave) {
      var index = this.lista
        .map((obj) => {
          return obj.clave;
        })
        .indexOf(clave);

      this.lista.splice(index, 1);

      firebase
        .database()
        .ref("vue-store/" + clave)
        .remove();
    },

    listarElementos: function () {
      var datos = firebase.database().ref("vue-store");
      datos.on("value", (snapshot) => {
        this.lista = [];
        snapshot.forEach((childSnapshot) => {
          var childData = childSnapshot.val();
          this.lista.push(childData);
        });
      });
    },
  },

  created: function () {
    this.listarElementos();
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
