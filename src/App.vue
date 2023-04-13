<template>
  <div>
    <CardPrincipal>
      <v-btn color="blue" @click="showModalInsert = true">Cadastrar</v-btn>
      <v-btn @click="showModal = true" color="error"> Todos </v-btn>
      <v-btn color="success" @click="showModalRapha = true">Rapha</v-btn>
    </CardPrincipal>
    <modal v-if="showModal">
      <div class="container">
        <v-btn class="ma-2" color="error" @click="showModal = false">X</v-btn>
      </div>
    </modal>
    <ModalRapha v-if="showModalRapha" title="Rapha ABR/2023">
      <div class="container">
        <v-btn class="ma-2" color="error" @click="showModalRapha = false"
          >X</v-btn
        >
      </div>
    </ModalRapha>
    <ModalInsert title="Cadastrar" v-if="showModalInsert">
      <div class="container">
        <v-btn class="ma-2" color="error" @click="showModalInsert = false"
          >X</v-btn
        >
      </div></ModalInsert
    >
  </div>
</template>
<script>
import lista from "./bd/bd";
import modal from "./components/modal.vue";
import CardPrincipal from "./components/CardPrincipal.vue";
import ModalRapha from "./components/ModalRapha.vue";
import ModalInsert from "./components/ModalInsert.vue";
export default {
  data() {
    return {
      showModal: false,
      showModalRapha: false,
      showModalInsert: false,
      lista,
    };
  },
  components: {
    modal,
    CardPrincipal,
    ModalRapha,
    ModalInsert,
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
