<template>
  <h1>{{ title }}</h1>
  <p>Weclome!</p>
  <input type="text" ref="name" />
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button v-on:click="toggleModal">open modal</button>
</template>
<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue app",
      header: "Sign up for the Giveaway!",
      text: "Grab your ninjia swag for half price!",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid grey;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
