<template>
  <div>
    <h1>{{ title }}</h1>
    <input type="text" ref="name" />
    <button @click="handleClick">click me</button>
    <div v-if="showModal">
      <Modal theme="sale" @close="toggleModal">
        <template v-slot:links>
          <a href="#">Sign up now </a>
          <a href="#">more info </a>
        </template>
        <h1>Hello</h1>
        <p>Me me</p>
      </Modal>
    </div>

    <button @click="toggleModal">open modal</button>
  </div>
</template>

<script>
import Modal from "./components/Modal";

export default {
  components: { Modal },
  name: "App",
  data() {
    return {
      title: "My first Vue App : )",
      showModal: false,
    };
  },

  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },

    toggleModal() {
      this.showModal = !this.showModal;
    },
  },

  component: {
    Modal,
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
  text-decoration: underline;
}
</style>
