<template>
  <div v-show="isVisible">
    <h1>{{ title }}</h1> 
    <button @click="isVisible = false">X</button>
    <div class="flex">
      <p>{{ description }}</p>
    </div>
  </div>
</template>



<script>
export default {
  name: "Card",
  props: ["title", "description"],
    data() {
    return {
      isVisible : true
    }
  },
  methods: {
    
  }
};
</script>


<style scoped>
</style>