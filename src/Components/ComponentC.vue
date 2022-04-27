<template>
  <h2>Component C</h2>
  <ComponentE />
</template>

<script>
import ComponentE from "./ComponentE.vue";
export default {
  components: { ComponentE },
  name: "ComponentC",
};
</script>

<style scoped></style>
