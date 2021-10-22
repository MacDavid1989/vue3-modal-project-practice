<template>
  <div class="backdrop" @click.self="closeModal">
    <div
      class="modal"
      :class="{ sale: theme == 'sale', congrats: theme == 'congrats' }"
    >
      <slot>Default Content</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal {
  width: 400px;
  padding-bottom: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.modal.sale {
  background: crimson;
  color: white;
}
.modal.congrats {
  background: black;
  color: blue;
}
.actions {
  text-align: center;
  margin: 30px 0 10px 0;
  color: #333;
}
.modal.sale .actions {
  color: white;
}
.modal.congrats .actions {
  color: blue;
}
</style>
