<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <book-item v-for="book in books" :key="book.id" :book="book"></book-item>
    </ul>
	<book-form @addBook='appendBook'></book-form>
  </div>
</template>

<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm";
export default {
  name: "BookList",
  components: {
	  BookItem,
	  BookForm,
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
  },
  methods: {
	  appendBook: function(bookTitle, bookAuthor){
		  this.books.push({ title: bookTitle, author: bookAuthor });
	  }
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