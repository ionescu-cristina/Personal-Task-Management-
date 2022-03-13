<template>
  <div class="modal flex">
    <div class="border">
      <h1>{{ title }}</h1>
      <p>{{ description }}</p>
    </div>
   <div> <button @click="$emit('close')">CLOSE</button></div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["title", "description"],
  data() {
    return {};
  },
};
</script>

<style scoped>
.modal {
  background-color: black;
  color: white;
  padding: 30px 0;
  margin: 30px 0;
}
</style>
