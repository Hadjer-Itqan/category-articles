<template>
    <v-row class="justify-center my-4">
        <v-col v-for="(item,index) in articles" :key="index" cols="4">
            <ArticleCard :article="item"></ArticleCard>
        </v-col>
    </v-row>
 </template>

<script setup>
import { useRoute } from 'vue-router'
import axios from 'axios'

const route = useRoute()
const id = route.params.id

const articles = ref([
    { id:1 , title:"title 01", content:'lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
    { id:13 , title:"title 01", content:'lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
    { id:15 , title:"title 01", content:'lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
    { id:133 , title:"title 01", content:'lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
    { id:193 , title:"title 01", content:'lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
    { id:1599 , title:"title 01", content:'lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
])


axios
.get(`url/articles/${id}`)
.then((response) => {
    //!incomment this
    //articles.value= response.data
    
})
.catch((error) => {
    console.log({ error })
})
</script>
 