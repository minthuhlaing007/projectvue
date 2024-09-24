<template>
  <div class="backdrop" @click.self="closeModal">
    <div
      class="modal"
      :class="{ success: theme === 'success',danger:theme==='delete'}"
    >
     <slot><h1>this is default slot</h1></slot>
     <slot name="links"/>
    </div>
  </div>
</template>

<script>
export default {
  props: [ "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.backdrop {
  width: 100%;
  height: 100%;
  position: fixed;
  top: 0;
  background: rgba(0, 0, 0, 0.5);
}
.modal {
  width: 500px;
  padding: 20px;
  margin: 200px auto;
  background: white;
  border-radius: 20px;
}
.success {
  background: green;
  color: white;
}
.danger{
  background:crimson;
  color:white;
}
</style>
