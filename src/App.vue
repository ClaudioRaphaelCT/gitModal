<template>
  <div>
    <h1 class="text-center mb-5">Utilizando Modal</h1>
    <v-card class="mx-auto" max-width="344" variant="outlined">
      <v-card-item>
        <div>
          <div class="text-h6 mb-1">Minha lista de compras</div>
          <div class="text-caption">compras referentes a março</div>
        </div>
      </v-card-item>
      <v-card-actions>
        <v-btn @click="showModal = true" color="error"> Visualizar </v-btn>
      </v-card-actions>
    </v-card>
    <div class="modal" v-if="showModal">
      <div class="modal-content">
        <v-btn @click="showModal = false" color="error">X</v-btn>
        <h3 class="text-center mb-5">Abril/2023</h3>
        <v-divider class="mb-3"></v-divider>
        <ul v-for="(item, indice) in lista" :key="indice">
          <li class="text-center">
            <h4>
              {{ item.nome }}, {{ item.produto }}, valor: R$ {{ item.valor }}
            </h4>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import lista from "./bd/bd";
export default {
  data() {
    return {
      showModal: false,
      lista,
    };
  },
};
</script>
<style>
.modal {
  position: fixed;
  z-index: 1;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.4);
}

.modal-content {
  background-color: #fefefe;
  margin: 15% auto;
  padding: 20px;
  border: 1px solid #888;
  width: 80%;
}

li {
  list-style: none;
}
</style>
