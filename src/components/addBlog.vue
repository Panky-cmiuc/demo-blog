<template>
  <div id="addBlog">
        <h2>Add a blog</h2>
        <form id="addBlogForm">
            <label for="title">Blog title</label>
            <input type="text" required placeholder="Blog Title" v-model.lazy='blog.title'/>
            <label for="content">Your Blog</label>
            <textarea cols="30" rows="10" v-model.lazy='blog.content'></textarea>
            <div id="checkboxes">
            <label>Dogs</label>
            <input type="checkbox" v-model="blog.categories" value="Dogs">
            <label>Cats</label>
            <input type="checkbox" v-model="blog.categories" value="Cats">
            <label>Bats</label>
            <input type="checkbox" v-model="blog.categories" value="Bats">
            <label>Apes</label>
            <input type="checkbox" v-model="blog.categories" value="Apes">
        </div>

        <label>Authors</label>
        <select id="authors" v-model="blog.author">
            <option>Select</option>
            <option v-for="author in authors" v-bind:key="author">{{ author }}</option>
        </select>

        </form>

        <div id="preview">
            <h3>Preview</h3>
            <p>Blog title: {{ blog.title }}</p>
            <p>Blog content: </p>
            <p>{{ blog.content }}</p>
            <p>Blog categories:</p>
            <ul>
                <li v-for="category in blog.categories" v-bind:key="category">{{ category }}</li>
            </ul>
            <p v-if="blog.author==='Select'">Blog Author:</p>
            <p v-else>Blog Author: {{ blog.author }}</p>
        </div>
        
  </div>
</template>

<script>
export default {
    components: {
    },
    data(){
        return{
        blog:{
            title:'',
            content:'',
            categories:[],
            author:'Select'
        },
        authors:[
            'Apple Man',
            'Candy Man',
            'The Nutcracker',
            'The Gambit'
        ], 
        }
    }
}
</script>

<style>
#addBlog *{
    box-sizing: border-box;
}
#addBlog{
    margin: 20px auto;
    max-width: 500px;
}
label{
    display: block;
    margin: 20px 0 10px;
}
input[type="text"], textarea{
    display: block;
    width: 100%;
    padding: 8px;
}
#preview{
    padding: 10px 20px;
    border: 1px dotted #ccc;
    margin: 30px 0;
}
h3{
    margin-top: 10px;
}
#checkboxes input{
    display: inline-block;
    margin-right: 20px;
}
#checkboxes label{
    display: inline-block;
}
li{
    display: inline-block;
    margin-right: 20px;
}
ul{
    padding: 0;
}
</style>