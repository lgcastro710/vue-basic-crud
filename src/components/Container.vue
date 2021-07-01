<template>
  <div class="mx-auto">
    <Nav :lista="lista"></Nav>

    <div class="flex p-4 flex-col md:flex-row">
      <div class="p-4 box-border w-full md:w-96">
        <Form :agregar="agregar"></Form>
      </div>
      <div class="box-border" style="width: 100%">
        <List :lista="lista" :eliminar="eliminar" :agregar="agregar"></List>
      </div>
    </div>
  </div>
</template>

<script>
import Form from "./Form";
import List from "./List";
import Nav from "./Nav";
import firebase from "../../firebase";

export default {
  name: "Container",

  components: {
    Form,
    List,
    Nav,
  },
  data: () => ({
    lista: [],
  }),
  methods: {
    listarElementos: function () {
      const datos = firebase.database().ref("vue-store");
      datos.on("value", (snapshot) => {
        this.lista = [];
        snapshot.forEach((childSnapshot) => {
          const childData = childSnapshot.val();
          if (
            childData.imageUrl === "" ||
            (childData.imageUrl.slice(0, 4) !== "http" &&
              childData.imageUrl.slice(0, 4) !== "data")
          ) {
            console.log(childData.imageUrl.slice(0, 4));
            childData.imageUrl = require("../assets/bg-not-found.png");
          }
          this.lista.push(childData);
        });
      });
    },

    agregar: function (clave, nombre, descripcion, imageUrl, precio) {
      const item = { clave, nombre, descripcion, imageUrl, precio };
      firebase
        .database()
        .ref("vue-store/" + clave)
        .set(item);
    },

    eliminar: function (clave) {
      const index = this.lista
        .map(function (obj) {
          return obj.clave;
        })
        .indexOf(clave);

      this.lista.splice(index, 1);
      firebase
        .database()
        .ref("vue-store/" + clave)
        .remove();
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
  color: #fff;
}
</style>
