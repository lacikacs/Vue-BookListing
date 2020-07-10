<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <book-item v-for="book in books" :key="book.id" :book="book"></book-item>
    </ul>
  </div>
</template>

<script>
import BookItem from "./BookItem";
export default {
  name: "BookList",
  components: {
	  BookItem,
  },
  data: function() {
    return {
      title: "All Books",
      books: [
        { id: 1, title: "Self-Reliance", author: "Ralph Waldo Emerson" },
        { id: 2, title: "American Gods", author: "Neil Gaiman" },
        { id: 3, title: "Amusing Ourselves to Death", author: "Neil Postman" }
      ]
    };
  }
};
</script>

<style scoped>
h1,
h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}
</style>