<template>
  <div>
    <form class action="#" method="post" @submit.prevent="bookSubmit(bookTitle, bookAuthor)">
      <input type="text" name="title" value placeholder="Book Title" v-model="bookTitle">
      <input type="text" name="author" value placeholder="Book Author" v-model="bookAuthor">
      <button type="submit" name="button">Add Book</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  methods: {
    bookSubmit(bookTitle, bookAuthor) {
      this.$emit("addBook", bookTitle, bookAuthor);
    }
  },
  data() {
    return {
      bookTitle: "",
      bookAuthor: ""
    };
  }
};
</script>

<style scoped>
</style>