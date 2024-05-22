<template>
    <div class="book-item" @click="showDetails">
      <h2>{{ book.title }}</h2>
      <p>by {{ book.author }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['book'],
    methods: {
      showDetails() {
        this.$emit('show-details', this.book);
      }
    }
  };
  </script>
  
  <style>
  .book-item {
    border: 1px solid #ccc;
    padding: 10px;
    margin-bottom: 10px;
    cursor: pointer;
    transition: background 0.3s;
  }
  .book-item:hover {
    background: #f0f0f0;
  }
  </style>
  