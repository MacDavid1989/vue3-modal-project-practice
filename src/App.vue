<template>
  <h1>{{ title }}</h1>
  <Modal header="Sign up for the Giveaway" />
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue3 App :)",
    };
  },
};
</script>
