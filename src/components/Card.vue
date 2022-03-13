<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="flex">
      <p>{{ description }}</p>
    </div>
  </div>
</template>



<script>
export default {
  name: "Card",
  props: ["title", "description"],
};
</script>


<style scoped>
</style>