<template>
  <h3 v-for="name in names" :key="name.firstName">
    <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
  </h3>
</template>

<script>
export default {
  name: "NameList",
  data() {
    return {
      names: [
        {
          firstName: "Anirudh",
          lastName: "Panda",
        },
        {
          firstName: "Avanti",
          lastName: "Panda",
        },
        {
          firstName: "Avinash",
          lastName: "Panda",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
