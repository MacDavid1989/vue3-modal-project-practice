<template>
  <h1>{{ title }}</h1>
  <p>{{ welcome }}</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>Ninja Giveaway!</h1>
      <p>Grab your ninja swag for half price!</p>
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">More Info</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
  <div v-if="showCongratsModal">
    <Modal theme="congrats" @close="toggleCongratsModal">
      <h1>Congratulations!</h1>
      <p>You're the lucky winner!</p>
      <template v-slot:links>
        <a href="#">Claim Prize</a>
        <a href="#">More Info</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleCongratsModal">Click Me</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First Vue3 App :)",
      welcome: "Welcome...",
      showModal: false,
      showCongratsModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleCongratsModal() {
      this.showCongratsModal = !this.showCongratsModal;
    },
  },
};
</script>
