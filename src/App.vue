<template>
  <div>
    <h1 class="text-center mb-5">Utilizando Modal</h1>
    <v-card class="mx-auto" max-width="344" variant="outlined">
      <v-card-item>
        <div>
          <div class="text-h6 mb-1">Minha lista de compras</div>
          <div class="text-caption">Compras referentes a Abril</div>
        </div>
      </v-card-item>
      <v-card-actions>
        <v-btn @click="showModal = true" color="error"> Visualizar </v-btn>
      </v-card-actions>
    </v-card>

    <modal v-if="showModal" title="ABR/2023">
      <div class="container">
        <v-btn class="ma-2" color="error" @click="showModal = false">X</v-btn>
      </div>
    </modal>
  </div>
</template>
<script>
import lista from "./bd/bd";
import modal from "./components/modal.vue";
export default {
  data() {
    return {
      showModal: false,
      lista,
    };
  },
  components: {
    modal,
  },
};
</script>
<style>
.container {
  position: relative;
}

.v-btn.ma-2 {
  position: absolute;
  top: 0;
  right: 0;
}
</style>
