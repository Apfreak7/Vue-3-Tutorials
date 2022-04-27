<template>
  <div>
    <h2>Article Component</h2>
    <h2 v-bind="$attrs">{{ title }}</h2>
    <h2>Likes - {{ likes }}</h2>
    <h2>Published - {{ isPublished ? "Yes" : "No" }}</h2>
    <input type="text" v-model="name" />
  </div>
</template>

<script>
export default {
  name: "MyArticle",
  props: {
    title: {
      type: String,
      required: true,
      default: "Article default title",
    },
    likes: Number,
    isPublished: Boolean,
  },
  data() {
    return {
      name: "",
    };
  },
  inheritAttrs: false,
};
</script>

<style scoped></style>
