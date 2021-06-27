<template>
  <div class="col-12">
    <form>
      <div class="form-group">
        <label for="clave">Clave</label>
        <input type="text" class="form-control" id="clave" v-model="clave" />
      </div>
      <div class="form-group">
        <label for="titulo">Titulo</label>
        <input type="text" class="form-control" id="titulo" v-model="titulo" />
      </div>
      <div class="form-group">
        <label for="descripcion">Descripcion</label>
        <input
          type="text"
          class="form-control"
          id="descripcion"
          v-model="descripcion"
        />
      </div>
      <button
        class="btn btn-primary"
        v-on:click.prevent="agregar(clave, titulo, descripcion)"
      >
        <i class="fa fa-save"></i> Guardar
      </button>
    </form>
    <hr />
  </div>
</template>

<script>
export default {
  data() {
    return {
      clave: "1",
      titulo: "correr",
      descripcion: "ejercicios",
    };
  },
  props: {
    agregar: Function,
  },
};
</script>