<template>
  <input
    type="text"
    :value="modelValue"
    @input="$emit('update: modelValue', $event.target.value)"
  />
</template>

<script>
export default {
  name: "MyInput",
  props: {
    modalValue: String,
  },
};
</script>

<style scoped>
input[type="text"] {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.4;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
