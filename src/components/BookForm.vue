<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <div>
      <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    </div>
    <div>
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    </div>
    <div>
      <label for="finishedReading">
        <input v-model="bookData.finishedReading" type="checkbox">
        Finished Reading
      </label>
    </div>
    <div>
      <label for="borrowed">
        <input v-model="bookData.ownership" type="radio" value="borrowed">
        Borrowed
      </label>
      <label for="bought">
        <input v-model="bookData.ownership" type="radio" value="bought">
        Bought        
      </label>
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
