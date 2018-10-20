<template>
<div>
    <h1>{{title}}</h1>
    <ul>
        <book-item v-for="book in books" :book='book'></book-item>
    </ul>
    <hr>
    <book-form @addBook='appendBook'></book-form>
</div>    
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm';

export default {
name: "BookList", 
components: {
    BookItem,
    BookForm
},
data() {
    return {
        title: 'All Books',
        books:[
            {title:'Gay dude', author: 'Mr.Phan'},
            {title:'Strong Man', author: 'Mr.Nhan'},
            {title:'Big Ball Sack', author: 'Mr.Nhan'},
        ]
        }
    },

methods: {
    appendBook(bookTitle, bookAuthor) { 
        this.books.push({ title:bookTitle, author: bookAuthor})
    }
    }
}
</script>

<style>
h1, h2{
    font-weight: normal
}
ul {
    list-style-type: none;
    padding: 0;
}

</style>
