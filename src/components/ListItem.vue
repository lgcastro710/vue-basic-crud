<template>
  <li
    class="md-layout-item md-medium-size-33 md-small-size-50 md-xsmall-size-100"
  >
    <!-- {{ item.clave }}-{{ item.titulo }} : {{ item.descripcion }} -->
    <!-- <button
          v-on:click.prevent="eliminar(item.clave)"
          class="btn btn-danger"
        >
          <i class="fa fa-trash"></i>
        </button> -->

    <Card>
      <md-card>
        <md-card-media>
          <!-- <img src="/assets/examples/card-image-1.jpg" alt="People"> -->
        </md-card-media>

        <md-card-header>
          <div class="md-title">{{ item.producto }}</div>
          <div class="md-subhead">$:{{ item.precio }}</div>
        </md-card-header>

        <md-card-expand>
          <md-card-actions md-alignment="space-between">
            <div>
              <md-button
                v-on:click.prevent="eliminar(item.clave)"
                class="md-raised md-accent md-button-p"
              >
                <i class="fa fa-trash"></i>
              </md-button>
            </div>

            <md-card-expand-trigger>
              <md-button>Learn more</md-button>
            </md-card-expand-trigger>
          </md-card-actions>

          <md-card-expand-content>
            <md-card-content>
              {{ item.descripcion }}
            </md-card-content>
          </md-card-expand-content>
        </md-card-expand>
      </md-card>
    </Card>
  </li>
</template>

<script>
import Card from "../components/ui/Card.vue";
export default {
  props: {
    item: Object,
    eliminar: Function,
  },
  components: {
    Card,
  },
};
</script>
<style  scoped>
li {
  margin: 0;
}
.card-expansion {
  height: 480px;
}

.md-card {
  width: 320px;
  margin: 4px;
  display: inline-block;
  vertical-align: top;
}
.md-button-p {
  min-width: 20px !important;
  height: 30px !important;
}
</style>