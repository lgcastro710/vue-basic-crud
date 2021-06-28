<template>
  <button v-on:click.prevent="onClick()" class="card-view">
    {{ title }}
  </button>
</template>
<script>
export default {
  name: "Button",
  props: {
    title: String,
    onClick: Function,
  },
};
</script>