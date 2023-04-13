<template>
  <div class="modal">
    <div class="modal-content">
      <slot></slot>
      <br />
      <h3 class="text-center">{{ title }}</h3>
      <v-divider class="mb-5"></v-divider>
      <ul v-for="(item, indice) in filteredRapha" :key="indice">
        <li>
          <h4 class="mb-1 mt-1">
            {{ item.nome }}, {{ item.produto }}, R${{ item.valor }}
          </h4>
        </li>
      </ul>
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
    };
  },
  computed: {
    filteredRapha() {
      return this.lista.filter((e) => {
        return e.nome == "Raphael";
      });
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
