<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <!-- <li v-for="book in books">{{book.title}}:{{book.author}}</li> -->
            <book-item v-for="book in books" :book='book'></book-item>
        </ul>
        <hr>
        <book-form @addBook="appendBook"></book-form>
    </div>
</template>

<script>
import BookItem from './BookItem';
import BookForm from './BookForm'

export default {
    name:'BookList',
    components: {
        BookItem,
        BookForm
    },
    data() {
        return {
            title: 'All Books',
            books: [
                {title:'Self-Reliance',author:'Ralph Waldo Emerson'},
                {title:'American Gods', author:'Neil Galman'},
                {title:'Amusing Ourlselves to Death', author:'Neil Postman'}
            ]
        }

    },
    methods: {
        appendBook(bookTitle, bookAuthor){
            this.books.push({title: bookTitle, author: bookAuthor});
        }
    }
}
</script>

<style>
h1,h2 {
    font-weight: normal  
}   
ul {
    list-style-type: none;
    padding: 0;
} 
li {
    display: block;
    margin: 0 10px;
}
</style>

