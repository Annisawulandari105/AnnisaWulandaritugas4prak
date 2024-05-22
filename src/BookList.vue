<template>
    <div class="book-list">
      <h1>Book List</h1>
      <book-item 
        v-for="book in books" 
        :key="book.id" 
        :book="book" 
        @show-details="showDetails"
      />
      <book-details 
        v-if="selectedBook" 
        :book="selectedBook"
        @close-details="selectedBook = null"
      >
        <p>Additional information about the book: {{ selectedBook.title }}</p>
      </book-details>
    </div>
  </template>
  
  <script>
  import BookItem from './BookItem.vue';
  import BookDetails from './BookDetails.vue';
  
  export default {
    components: {
      BookItem,
      BookDetails
    },
    data() {
      return {
        books: [
          { id: 1, title: '1984', author: 'George Orwell' },
          { id: 2, title: 'To Kill a Mockingbird', author: 'Harper Lee' },
          // Add more book objects here
        ],
        selectedBook: null
      };
    },
    methods: {
      showDetails(book) {
        this.selectedBook = book;
      }
    }
  };
  </script>
  
  <style>
  .book-list {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
  }
  </style>
  
