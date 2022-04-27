<template>
  <div>Hello {{ name }} a.k.a {{ heroName }}!</div>
</template>

<script>
export default {
  name: "MyGreet",
  props: ["name", "heroName"],
};
</script>

<style scoped></style>
