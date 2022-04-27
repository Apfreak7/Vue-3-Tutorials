<template>
  <h2>Component E</h2>
  <ComponentF />
</template>

<script>
import ComponentF from "./ComponentF.vue";
export default {
  components: { ComponentF },
  name: "ComponentE",
};
</script>

<style scoped></style>
