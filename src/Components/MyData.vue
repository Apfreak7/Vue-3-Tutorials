<template>
  <h2>Options - {{ o_firstName }}</h2>
  <h2>Options - {{ o_firstName }} {{ o_lastName }} a.k.a {{ o_heroName }}</h2>

  <h2>Composition - {{ c_firstName }} {{ c_lastName }} {{ c_heroName }}</h2>
  <h2>Composition - {{ greetHero }}</h2>

  <h2>
    Composition - {{ state.firstName }} {{ state.lastName }}
    {{ state.heroName }}
  </h2>
  <h2>Composition - {{ reactiveGreetHero }}</h2>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "MyData",
  setup() {
    const c_firstName = ref("Avanti");
    const c_lastName = ref("Panda");
    const c_heroName = ref("Batman");

    c_firstName.value = "Avinash";
    const greet = `Hello ${c_firstName.value}`;
    const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`;
    console.log("c_firstName", c_firstName);

    const state = reactive({
      firstName: "Namita",
      lastName: "Panda",
      heroName: "Wonder Woman",
    });

    const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} a.k.a ${state.heroName}`;

    return {
      c_firstName,
      c_lastName,
      c_heroName,
      greet,
      greetHero,
      reactiveGreetHero,
    };
  },
  data() {
    return {
      o_firstName: "Anirudh",
      o_lastName: "Panda",
      o_heroName: "Superman",
    };
  },
};
</script>

<style scoped></style>
