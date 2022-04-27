<template>
  <div>Options API Lifecycle Hooks</div>
</template>

<script>
export default {
  name: "LifecycleO",
  beforeCreate() {
    console.log("LifecycleO beforeCreate()");
  },
  created() {
    console.log("LifecycleO created()");
  },
  beforeMount() {
    console.log("LifecycleO beforeMount()");
  },
  mounted() {
    console.log("LifecycleO mounted()");
  },
  beforeUpdate() {
    console.log("LifecycleO beforeUpdate()");
  },
  updated() {
    console.log("LifecycleO updated()");
  },
  beforeUnmount() {
    console.log("LifecycleO beforeUnmount()");
  },
  unmounted() {
    console.log("LifecycleO unmounted()");
  },
};
</script>

<style scoped></style>
