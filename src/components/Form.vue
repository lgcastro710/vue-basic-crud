<template>
  <div class="col-4">
    <form>
      <div class="form-group">
        <label for="clave">Clave</label>
        <input
          type="text"
          class="form-control"
          id="clave"
          v-model="clave"
          placeholder="Ingresa una clave"
        />
      </div>
      <div class="form-group">
        <label for="producto">Producto</label>
        <input
          type="text"
          class="form-control"
          id="producto"
          v-model="producto"
          placeholder="Ingresa una producto"
        />
      </div>
      <div class="form-group">
        <label for="precio">Precio</label>
        <input
          type="text"
          class="form-control"
          id="precio"
          v-model="precio"
          placeholder="Ingresa una precio"
        />
      </div>
      <div class="form-group">
        <label for="descripcion">Descripcion</label>
        <textarea
          type="text"
          class="form-control"
          id="descripcion"
          v-model="descripcion"
          placeholder="Ingresa una descripcion"
        />
      </div>
      <!-- <button
        class="btn btn-primary"
        v-on:click.prevent="agregar(clave, titulo, descripcion)"
      >
        <i class="fa fa-save"></i> Guardar
      </button> -->
      <md-button
        class="md-raised md-primary"
        v-on:click.prevent="agregar(clave, producto, precio, descripcion)"
      >
        <i class="fa fa-save m-2"></i>Guardar
      </md-button>
    </form>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      clave: "",
      producto: "",
      precio: "",
      descripcion: "",
    };
  },
  props: {
    agregar: Function,
  },
};
</script>