<template>
  <h1 ref="heading">Hello world</h1>
  <p ref="para">
    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Consequuntur,
    laboriosam? Recusandae, cum. Dolor perspiciatis exercitationem eaque illo
    dolore deleniti tempore, sed, dolores placeat officiis asperiores. Error
    inventore in labore ratione?
  </p>
  <button @click.shift="changeHandler">shift click</button>
  <br />
  <teleport to=".modal" v-if="showModal">
    <Modal
      :theme="theme"
      @close="showModal = false"
    > 
    <h1>Hello World</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste reprehenderit laudantium minima fugiat dolorem porro unde ducimus autem sit nisi perspiciatis nam, sint quidem eos officiis libero. Reprehenderit, aspernatur unde!</p> 
    <template v-slot:links>
      <ul>
        <li>Number One</li>
        <li>number two</li>
        <li>number three</li>
      </ul>
    </template>
  </Modal>
  </teleport>

  <teleport to=".modal" v-if="deleteModal">
    <Modal
      theme="delete"
      @close="deleteModal = false"
    > 
    <h1>Are you sure you want to delete???</h1>
    <p>See you Next time!!!!</p> 
    <template v-slot:links>
      <ul>
        <li> One</li>
        <li> two</li>
        <li> three</li>
      </ul>
    </template>
  </Modal>
  </teleport>
  
  <button @click="showModal = true">Show Model</button>
  <button @click="deleteModal = true">Delete Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  data() {
    return {
      header: "login success",
      content: "welcome user min thu hlaing",
      theme: "success",
      showModal: false,
      deleteModal: false,
    };
  },
  methods: {
    changeHandler() {
      this.$refs.heading.textContent = "John Doe";
      this.$refs.para.textContent = "This is my story";
      this.$refs.heading.style.fontSize = "100px";
      this.$refs.heading.style.color = "crimson";
      this.$refs.para.style.fontFamily = "monospace";
      this.$refs.para.style.color = "navy";
    },
  },
  components: {
    Modal
  },
};
</script>

<style scoped>
h1 {
  color: gray;
}
</style>
