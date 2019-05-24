<template>
  <form v-on:submit.prevent="bookSubmit(bookData)" class="" action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value="" placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value="" placeholder="Book Author">
    <div>
      <label for="finishingReading">
        Finished Reading
        <input type="checkbox" v-model="bookData.finishingReading" />
      </label>
    </div>
    <div>
      <label for="ownership">
        Borrowed
        <input type="checkbox" v-model="bookData.borrowed" value="borrowed" />
      </label>
      <label for="ownership">
        Ownership
        <input type="checkbox" v-model="bookData.ownership" value="bought" />
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
