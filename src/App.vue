<template>
  <h1>{{ title }}</h1>
  <Modal :header="header" :text="text" theme="sale" />
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
    };
  },
};
</script>
