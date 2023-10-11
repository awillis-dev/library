<template>
  <div class="p-4 flex justify-center">
    <button @click="showForm = !showForm" class="btn">Add Book</button>
  </div>

  <div v-if="showForm">
    <input v-model="title" placeholder="Title" />
    <input v-model="author" placeholder="Author" />
    <input v-model="pages" placeholder="Pages" />
    <input v-model="read" placeholder="Read?" type="checkbox" />
    <button @click="addBookToLibrary">Submit</button>
  </div>

  <ul>
    <li v-for="book in myLibrary" :key="book.title">
      {{ book.title }}
      {{ book.author }}
      {{ book.pages }}
      {{ book.read }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      myLibrary: [],
      showForm: false,
      title: "",
      author: "",
      pages: 0,
      read: false,
    };
  },
  methods: {
    addBookToLibrary() {
      if (this.title && this.author && this.pages && this.read) {
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
