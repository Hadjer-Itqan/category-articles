<template>
  <v-app>
    <v-app-bar > 
      <v-list-item link >
        <v-avatar >
          <v-img
            alt="John"
            src="https://cdn.vuetifyjs.com/images/john.jpg"
          ></v-img>
        </v-avatar>
      </v-list-item>
      <v-list-item link title="Home" to="/home"></v-list-item>
      <v-list-item  v-for="(item,index) in categories"  :key="index" :title="item.name" :to="`/categories/${item.id}`"></v-list-item>
    </v-app-bar>
    <v-main>
      <router-view />
    </v-main>

  </v-app>
</template>

<script setup>

import axios from 'axios'

const categories = ref([
    {
        id:1, name:"name 01",
    },
    {
        id:11, name:"name 031", 
    },
    {
        id:12, name:"name 021", 
    }
])

axios
.get("url/categories")
.then((response) => {
    //!incomment this
    //recentArticles.value= response.data
    
})
.catch((error) => {
    console.log({ error })
})

</script>
