<template>
  <div>
    <h1 class="text-center mb-4">Card</h1>

    <v-card class="mx-auto" max-width="344" variant="outlined">
      <v-card-item>
        <div>
          <div class="text-h6 mb-1">Minha lista de compras</div>
          <div class="text-caption">Compras referentes a Abril</div>
        </div>
      </v-card-item>
      <v-card-actions>
        <slot></slot>
      </v-card-actions>
    </v-card>
  </div>
</template>
<script>
import moment from "moment";
export default {
  data() {
    return {
      now: moment().format("DD/MM/YYYY HH:mm"),
    };
  },
};
</script>
<style scoped></style>
