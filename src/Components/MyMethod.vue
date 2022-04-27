<template>
  <div>
    <h2>{{ name }}</h2>
    <button @click="setName">Change Name</button>

    <h2>{{ count }}</h2>
    <button @click="incrementCount">Increment Count</button>

    <h2>{{ first }} {{ last }}</h2>
    <button @click="changeText">Change text</button>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from "vue";
export default {
  name: "MyMethod",
  setup() {
    const count = ref(0);
    const state = reactive({
      first: "Anirudh",
      last: "Panda",
    });

    function incrementCount() {
      count.value++;
    }

    function changeText() {
      state.first = "Namita";
      state.last = "Panda";
    }

    return {
      count,
      incrementCount,
      ...toRefs(state),
      changeText,
    };
  },
  data() {
    return {
      name: "Anirudh",
    };
  },
  methods: {
    setName() {
      this.name = "Namita";
    },
  },
};
</script>

<style scoped></style>
