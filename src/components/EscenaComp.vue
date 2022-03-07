<template>
  <div class="mx-3">
    <p class="mb-0 px-4 py-3 text-center">{{ myEscena }}</p>
  </div>
</template>

<script>
export default {
  props: ["myEscena", "myImg"],
};
</script>

<style scoped>
div {
  background: gainsboro;
  opacity: 0.6;
}
</style>
