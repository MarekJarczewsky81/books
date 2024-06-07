<template>
  <div id="app">

    <!-- heading -->
    <header>
      <h1>Books<span>.app</span></h1>
    </header>

    <!-- books list -->
    <ul>
      <li
        :key="index"
        v-for="(book, index) in books">
        {{ book.title }} {{ book.price }}
        <button @click="removeBook(index)">Remove</button>
      </li>
    </ul>

    <!-- no books message -->
    <p v-show="!books.length">No books...</p>
    <p v-if="books.length === 1">One book</p>
    <p v-else-if="books.length > 1">Many books!</p>

    <!-- add book form -->
    <form>
      <label>
        Title:
        <input type="text" name="title">
      </label>
      <label>
        price:
        <input type="number" name="price">
      </label>
      <button>Add book</button>
    </form>

  </div>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    books: [
      {
        title: 'The Catcher in the Rye',
        price: 20
      },
      {
        title: 'Of Mice and Men',
        price: 18
      }
    ]
  }),
  methods: {
    removeBook (index) {
      this.books.splice(index, 1)
    }
  }
}
</script>
