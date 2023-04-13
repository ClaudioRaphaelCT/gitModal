<template>
  <div class="modal">
    <div class="modal-content">
      <slot></slot>
      <br />
      <h3 class="text-center">{{ title }}</h3>
      <v-divider class="mb-5"></v-divider>
      <v-text-field label="Nome" v-model="name"></v-text-field>
      <v-text-field label="Produto" v-model="product"></v-text-field>
      <v-text-field label="Valor" v-model="valorProd"></v-text-field>
      <v-btn block color="primary" dark @click="handleInsert">Confirmar</v-btn>
    </div>
  </div>
</template>
<script>
import lista from "../bd/bd";
export default {
  props: ["title"],
  data() {
    return {
      lista,
      name: "",
      product: "",
      valorProd: null,
    };
  },
  methods: {
    handleInsert() {
      this.lista.push({
        nome: this.name,
        produto: this.product,
        valor: this.valorProd,
      });
      this.name = "";
      this.product = "";
      this.valorProd = "";
      alert("Cadastro realizado com sucesso!");
      console.log(this.lista);
    },
  },
};
</script>
<style scoped>
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
  padding: 10px;
  border: 1px solid #888;
  width: 40%;
}

li {
  list-style: none;
}
</style>
