<template>
  <div class="col-12">
    <div class="flex p-4">
      <input
        type="text"
        class="form-control search-input"
        v-model="txtBuscar"
        placeholder="Buscar"
      />
      <ButtonSquare :data="{}" :onClick="() => {}" bg="#48cdfb">
        <i class="fa fa-search"></i>
      </ButtonSquare>
    </div>
    <ShowProductModal
      v-if="item"
      :onClose="onClose"
      :data="item"
    ></ShowProductModal>
    <EditProductModal
      v-if="itemEdit"
      :data="itemEdit"
      :onCloseEdit="onCloseEdit"
      :agregar="agregar"
    ></EditProductModal>
    <ul class="flex" style="flex-wrap: wrap">
      <LisItem
        v-for="(product, key) in listaFiltrada"
        v-bind:key="key"
        :product="product"
        :eliminar="eliminar"
        :setItem="setItem"
        :setEdit="setEdit"
        :setBager="setBager"
      ></LisItem>
    </ul>
  </div>
</template>

<script>
import LisItem from "./ListItem";
import ButtonSquare from "./ui/ButtonSquare";
import ShowProductModal from "./ShowProductModal";
import EditProductModal from "./EditProductModal";

export default {
  name: "List",
  props: {
    lista: Array,
    eliminar: Function,
    agregar: Function,
  },
  components: {
    LisItem,
    ButtonSquare,
    ShowProductModal,
    EditProductModal,
  },
  data: function () {
    return {
      txtBuscar: "",
      item: null,
      itemEdit: null,
    };
  },

  computed: {
    listaFiltrada: function () {
      let arreglo = this.lista;
      const consulta = this.txtBuscar;

      if (consulta !== "") {
        arreglo = this.lista?.filter(
          ({ nombre, descripcion, precio }) =>
            (
              nombre.toLowerCase() +
              " " +
              descripcion.toLowerCase() +
              " " +
              precio.toLowerCase()
            ).indexOf(consulta.toLowerCase()) > -1
        );
      }
      return arreglo;
    },
  },
  methods: {
    setItem: function (item) {
      console.log("item", item);
      this.item = item;
    },
    onClose: function () {
      console.log("cerrar");
      this.item = null;
    },
    onCloseEdit: function () {
      console.log("cerrar");
      this.itemEdit = null;
    },
    setEdit: function (item) {
      console.log("aqui", item);
      this.itemEdit = item;
    },
  },
};
</script>