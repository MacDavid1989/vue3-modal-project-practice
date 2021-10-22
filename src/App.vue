<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" />
  </div>
  <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue3 App :)",
      header: "Sign up for the Giveaway",
      text: "Grab your swag at half price!",
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
