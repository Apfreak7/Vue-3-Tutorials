<template>
  <div>
    <button @click="incrementCount">Clicked {{ count }} times</button>
  </div>
</template>

<script>
// import CounterMixin from "../Mixins/Counter";
import useCounter from "../Composables/useCounter";

export default {
  name: "ClickCounter",
  setup() {
    const { count, incrementCount } = useCounter();

    return {
      count,
      incrementCount,
    };
  },
  //   mixins: [CounterMixin],
};
</script>

<style scoped></style>
