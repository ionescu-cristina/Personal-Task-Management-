<template>
  <button @click="showLoginModal = true">SHOW FORM</button>

  <modal
    v-if="showLoginModal"
    title="Login Form"
    description="Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    @close="showLoginModal = false"
  ></modal>
</template>

<script>
import Modal from "../components/Modal.vue";
export default {
  name: "Login",
  components: {
    Modal,
  },
  data() {
    return {
      showLoginModal: false,
    };
  },
};
</script>
