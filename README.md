# Odin Project - JS Library

```js
const myLibrary = [];

function Book(title, author, pages, read) {
  this.title = title;
  this.author = author;
  this.pages = pages;
  this.read = read;
}

function addBookToLibrary(title, author, pages, read) {
  const newBook = new Book(title, author, pages, read);
  myLibrary.push(newBook);
}

addBookToLibrary("A Good Girl's Guide to Murder", "Holly Jackson", 400, true);
addBookToLibrary("Good Girl, Bad Blood", "Holly Jackson", 420, true);
addBookToLibrary("As Good As Dead", "Holly Jackson", 430, false);
addBookToLibrary("Vicious", "V.E. Schwab", 370, true);
addBookToLibrary("Vengeful", "V.E. Schwab", 480, true);

function displayLibrary(myLibrary) {
  myLibrary.forEach((book) => console.log(book));
}

displayLibrary(myLibrary);
```

---

## Setup

Make sure to install the dependencies:

```bash
# npm
npm install
```

## Development Server

Start the development server on `http://localhost:3000`:

```bash
# npm
npm run dev
```

## Production

Build the application for production:

```bash
# npm
npm run build
```

Locally preview production build:

```bash
# npm
npm run preview
```
