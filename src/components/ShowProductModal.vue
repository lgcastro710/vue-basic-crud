<template>
  <Modal :onClose="onClose" :title="data.nombre">
    <div>
      <img :src="data.imageUrl" style="width: 450px" />
    </div>
    <div class="mt-2">
      <p class="text-sm text-gray-500">
        {{ data.descripcion }}
      </p>
    </div>
  </Modal>
</template>
<script>
import Modal from "./ui/Modal";

export default {
  name: "ShowProductModal",
  components: {
    Modal,
  },
  props: {
    data: Object,
    onClose: Function,
  },
};
</script>