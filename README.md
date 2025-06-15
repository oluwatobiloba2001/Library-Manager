# Library Management System

## Overview

This JavaScript code provides a library management system that enables users to display books in a library, get summaries of books, filter books by authors, and calculate the total number of pages in the library's catalog. It leverages modern JavaScript features like `forEach`, `map`, `filter`, and `reduce`.

---

## Features

### 1. **Display Books in the Library**

The `displayBooks` function generates a formatted string that lists all the books in the library along with their authors and the number of pages.

### 2. **Get Book Summaries**

The `getBookSummaries` function retrieves the summary or description of each book in the library.

### 3. **Filter Books by Author**

The `getBooksByAuthor` function returns a list of books written by a specific author.

### 4. **Calculate Total Pages**

The `getTotalPages` function calculates the total number of pages across all the books in the library.

---

## Code Breakdown

### Library Data Structure

The library is represented as an array of objects, with each object containing:

* `title`: Title of the book.
* `author`: Author(s) of the book.
* `about`: A short description of the book.
* `pages`: The number of pages in the book.

### Core Functions

* **`displayBooks(catalog)`**
  **Input:** Array of book objects.
  **Output:** A formatted string listing the books in the library.

  ```javascript
  let output = 'Books in the Library:\n';

  catalog.forEach((book) => {
    output += `- ${book.title} by ${book.author} (${book.pages} pages)\n`;
  });

  return output;
  ```

* **`getBookSummaries(catalog)`**
  **Input:** Array of book objects.
  **Output:** An array of summaries/descriptions for each book.

  ```javascript
  return catalog.map((book) => book.about);
  ```

* **`getBooksByAuthor(catalog, author)`**
  **Input:** Array of book objects, author name (string).
  **Output:** A filtered array of books written by the specified author.

  ```javascript
  return catalog.filter((book) => book.author === author);
  ```

* **`getTotalPages(catalog)`**
  **Input:** Array of book objects.
  **Output:** Total number of pages across all books in the catalog.

  ```javascript
  return catalog.reduce((acc, book) => acc + book.pages, 0);
  ```

### Example Usage

```javascript
const libraryBooks = displayBooks(library);
const bookSummaries = getBookSummaries(library);
const booksByArvidKahl = getBooksByAuthor(library, 'Arvid Kahl');
const totalPagesOfBooksInLibrary = getTotalPages(library);

console.log(libraryBooks); // Lists all books with titles, authors, and pages
console.log(bookSummaries); // Lists all book summaries
console.log(booksByArvidKahl); // Lists books written by Arvid Kahl
console.log(totalPagesOfBooksInLibrary); // Displays the total number of pages
```

---

## Sample Output

### Display Books

```
Books in the Library:
- Your Next Five Moves: Master the Art of Business Strategy by Patrick Bet-David and Greg Dinkin (320 pages)
- Atomic Habits by James Clear (320 pages)
- Choose Your Enemies Wisely: Business Planning for the Audacious Few by Patrick Bet-David (304 pages)
...
```

### Get Book Summaries

```
[
  "A book on how to plan ahead",
  "A practical book about discarding bad habits and building good ones",
  ...
]
```

### Filter Books by Author

```
[
  {
    title: 'The Embedded Entrepreneur',
    author: 'Arvid Kahl',
    about: 'A book focusing on how to build an audience-driven business',
    pages: 308,
  },
  {
    title: 'Zero to Sold',
    author: 'Arvid Kahl',
    about: 'A book on how to bootstrap a business',
    pages: 500,
  }
]
```

### Total Pages

```
2504
```

---

## Requirements

* Node.js or a JavaScript runtime environment to execute the code.

---

## Future Improvements

* Add support for adding/removing books from the library.
* Implement search functionality to find books by keywords.
* Create a web interface to make the library more interactive.

---

## Author

This library system is a sample project designed to demonstrate efficient JavaScript coding practices for managing a collection of books.
