<template>
  <div>
    <input type="text" placeholder="Name" v-model="name" />

    <input type="text" placeholder="First Name" v-model="firstName" />
    <input type="text" placeholder="Last Name" v-model="lastName" />

    <input type="text" placeholder="Reactive First Name" v-model="fName" />
    <input type="text" placeholder="Reactive Last Name" v-model="lName" />
    <input
      type="text"
      placeholder="Reactive Hero Name"
      v-model="options.heroName"
    />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from "vue";
import _ from "lodash";

export default {
  name: "MyWatch",
  setup() {
    const state = reactive({
      fName: "",
      lName: "",
      options: {
        heroName: "",
      },
    });

    // watch(
    //   () => {
    //     return { ...state };
    //   },
    //   function (newValue, oldValue) {
    //     console.log("Fname old value", oldValue.fName);
    //     console.log("Fname new value", newValue.fName);
    //     console.log("lname old value", oldValue.lName);
    //     console.log("lname new value", newValue.lName);
    //   }
    // );

    watch(
      () => _.cloneDeep(state.options),
      function (newValue, oldValue) {
        console.log("Options old value", oldValue);
        console.log("Options new value", newValue);
      },
      {
        deep: true,
      }
    );

    const firstName = ref("");
    const lastName = ref("Panda");

    watch(
      [firstName, lastName],
      (newValues, oldValues) => {
        console.log("FirstName Old value", oldValues[0]);
        console.log("FirstName New value", newValues[0]);
        console.log("LastName Old value", oldValues[1]);
        console.log("LastName New value", newValues[1]);
      },
      {
        immediate: true,
      }
    );

    return {
      firstName,
      lastName,
      ...toRefs(state),
    };
  },
  data() {
    return {
      name: "",
    };
  },
  watch: {
    name(newValue, oldValue) {
      console.log("Old value", oldValue);
      console.log("New value", newValue);
    },
  },
};
</script>

<style scoped></style>
