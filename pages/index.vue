<template>
  <div class="p-4 flex justify-center">
    <button class="btn" @click="showForm = !showForm">
      <i class="material-icons mr-2 my-1">add</i>
      <span>Add Book</span>
    </button>
  </div>

  <div class="card text-center" v-if="showForm">
    <input class="input" v-model="title" placeholder="Title" />
    <input class="input" v-model="author" placeholder="Author" />
    <input class="input" v-model="pages" placeholder="Pages" />
    <input class="input" v-model="read" placeholder="Read?" type="checkbox" />
    <button class="submit-btn" @click="addBookToLibrary">Submit</button>
  </div>

  <div v-for="book in myLibrary" :key="book.title">
    <h3>{{ book.title }}</h3>
    <p>Author: {{ book.author }}</p>
    <p>Pages: {{ book.pages }}</p>
    <p>Read: {{ book.read ? "Yes" : "No" }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      myLibrary: [],
      showForm: false,
      title: "",
      author: "",
      pages: "",
      read: false,
    };
  },
  methods: {
    addBookToLibrary() {
      if (this.title && this.author && this.pages) {
        this.myLibrary.push({
          title: this.title,
          author: this.author,
          pages: this.pages,
          read: this.read,
        });
      }
      this.title = "";
      this.author = "";
      this.pages = 0;
      this.read = false;
      this.showForm = false;
    },
  },
};
</script>

<style scoped></style>
