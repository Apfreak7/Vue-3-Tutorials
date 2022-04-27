<template>
  <div>
    <h2>{{ firstName }} {{ lastName }}</h2>
  </div>
</template>

<script>
import { reactive, toRefs } from "vue";

export default {
  name: "DemoTwo",
  setup() {
    const state = reactive({
      firstName: "Anirudh",
      lastName: "Panda",
    });

    setTimeout(() => {
      state.firstName = "Namita";
      state.lastName = "Panda";
      console.log(state);
    }, 2000);

    return toRefs(state);
  },
};
</script>

<style scoped></style>
