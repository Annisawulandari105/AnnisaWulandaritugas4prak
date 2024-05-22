<template>
  <div class="book-details">
    <h2>{{ book.title }}</h2>
    <p>by {{ book.author }}</p>
    <slot>
      <p>No additional details available.</p>
    </slot>
    <button @click="$emit('close-details')">Close</button>
  </div>
</template>

<script>
export default {
  props: ['book']
};
</script>

<style>
.book-details {
  border: 1px solid #ccc;
  padding: 20px;
  background: #fafafa;
}
.book-details button {
  margin-top: 20px;
}
</style>
