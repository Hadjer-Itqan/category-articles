<template>
    <v-card
      class="mx-auto"
    >
      <v-img
        height="400px"
        :src="article.img"
        cover
      ></v-img>
  
      <v-card-title>
        {{article.title}}
      </v-card-title>
  
      <v-card-text>
        {{article.content}}
      </v-card-text>
    </v-card>
  </template>
 

<script setup>
import { useRoute } from 'vue-router'
import axios from 'axios'

const route = useRoute()
const id = route.params.id

const article = ref(
    { id:1 , title:"title 01", content:'lorem lorem ', img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'},
)


axios
.get(`url/article/${id}`)
.then((response) => {
    //!incomment this
    //article.value= response.data
    
})
.catch((error) => {
    console.log({ error })
})
</script>
 