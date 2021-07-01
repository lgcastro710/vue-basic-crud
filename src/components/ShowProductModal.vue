<template>
  <Modal :onClose="onClose" :title="data.nombre">
    <div>
      <div class="flex justify-center mt-2">
        <img :src="data.imageUrl" style="width: 450px" />
      </div>
      <div class="mt-2 card-title">
        <p class="text-sm text-gray-500">
          {{ data.descripcion }}
        </p>
      </div>
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
