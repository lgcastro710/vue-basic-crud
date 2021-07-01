<template>
  <li class="w-full p-4 md:w-1/2 lg:w-1/3">
    <Card style="padding: 0">
      <div class="card-header">
        <div class="card-title">{{ product.nombre }}</div>
        <ButtonSquare :data="product" :onClick="deleteProduct" bg="#f47477">
          <i class="fa fa-close"></i>
        </ButtonSquare>
      </div>
      <div class="card-body">
        <img :src="product.imageUrl" style="max-width: 173px; height: 205px" />
        <h2 class="card-description">
          {{ product.precio }}
        </h2>
      </div>
      <div class="row card-footer">
        <Button title="Ver" :onClick="setItemSelected" :data="product"></Button>
        <Button
          title="Editar"
          :onClick="editSelected"
          :data="product"
          class="m-1"
        ></Button>
      </div>
    </Card>
  </li>
</template>

<script>
import Card from "./ui/Card";
import ButtonSquare from "./ui/ButtonSquare";
import Button from "./ui/Button";

export default {
  name: "ListItem",

  props: {
    product: Object,
    eliminar: Function,
    setItem: Function,
    setEdit: Function,
  },
  components: {
    Card,
    ButtonSquare,
    Button,
  },
  methods: {
    deleteProduct: function (data) {
      this.eliminar(data.clave);
    },
    setItemSelected: function (item) {
      this.setItem(item);
    },
    editSelected: function (item) {
      console.log("llega chiruli", item);
      this.setEdit(item);
    },
  },
};
</script>