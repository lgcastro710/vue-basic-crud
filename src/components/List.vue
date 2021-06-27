<template>
  <div class="col-12">
    <div class="input-group mb-3">
      <div class="input-group-prepend">
        <span class="input-group-text" id="basic-addon1"
          ><i class="fa fa-search"></i
        ></span>
      </div>
      <input type="text" class="form-control" v-model="txtBuscar" />
    </div>
    <ul class="list-group">
      <li
        v-for="(item, key) in listaFiltrada"
        v-bind:key="key"
        class="list-group-item"
      >
        {{ item.clave }}-{{ item.titulo }} : {{ item.descripcion }}
        <button
          v-on:click.prevent="eliminar(item.clave)"
          class="btn btn-danger"
        >
          <i class="fa fa-trash"></i>
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
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