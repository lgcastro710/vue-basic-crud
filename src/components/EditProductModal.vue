<template>
  <Modal :onClose="onCloseEdit" title="Editar producto">
    <form class="text-center px-6 py-4 shadow-lg" action="#" method="POST">
      <div class="">
        <input
          id="nombre"
          type="text"
          placeholder="Nombre"
          class="form-control search-input border"
          v-model="nombre"
          v-on:keypress="onChangeDataFrom"
        />

        <input
          id="precio"
          type="text"
          placeholder="Precio"
          class="form-control search-input border"
          v-model="precio"
          v-on:keypress="onChangeDataFrom"
        />

        <input
          id="imageUrl"
          type="text"
          placeholder="Imagen URL"
          class="form-control search-input border"
          v-model="imageUrl"
        />

        <textarea
          class="h-24 form-control search-input border"
          v-model="descripcion"
          placeholder="Descripcion"
          v-on:keypress="onChangeDataFrom"
        />
      </div>
      <div>
        <p>{{ message }}</p>
      </div>

      <Button :onClick="editProduct">Guardar</Button>
    </form>
  </Modal>
</template>
<script>
import Modal from "./ui/Modal";
import Button from "./ui/Button";

export default {
  name: "EditProductModal",
  data: function () {
    return {
      clave: this.data.clave,
      nombre: this.data.nombre,
      descripcion: this.data.descripcion,
      imageUrl: this.data.imageUrl,
      precio: this.data.precio,
      message: "",
    };
  },
  components: {
    Modal,
    Button,
  },
  props: {
    data: Object,
    onCloseEdit: Function,
    agregar: Function,
  },
  methods: {
    onChangeDataFrom: function () {
      this.message = "";
    },
    editProduct: function () {
      this.agregar(
        this.clave,
        this.nombre,
        this.descripcion,
        this.imageUrl,
        this.precio
      );
      this.onCloseEdit();
    },
  },
};
</script>
