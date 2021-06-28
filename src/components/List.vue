<template>
  <div class="col-8">
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1"
          ><i class="fa fa-search"></i
        ></span>
      </div>
      <input type="text" class="form-control" v-model="txtBuscar" />
    </div>
    <ul class="md-layout md-gutter md-alignment-center">
      <ListItem
        v-for="(item, key) in listaFiltrada"
        v-bind:key="key"
        :item="item"
        :eliminar="eliminar"
        class="row"
      ></ListItem>
    </ul>
  </div>
</template>

<script>
import ListItem from "./ListItem";

export default {
  components: {
    ListItem,
  },
  data() {
    return {
      txtBuscar: "",
    };
  },
  props: {
    lista: Array,
    eliminar: Function,
  },
  computed: {
    listaFiltrada: function () {
      var arreglo = this.lista;
      var consulta = this.txtBuscar;

      if (consulta !== "") {
        arreglo = arreglo.filter(function (obj) {
          return (
            (
              obj.titulo.toLowerCase() +
              " " +
              obj.descripcion.toLowerCase()
            ).indexOf(consulta.toLowerCase()) > -1
          );
        });
      }

      return arreglo;
    },
  },
};
</script>
<style>
</style>