<template>
    <v-app>
      <v-container>
        <v-carousel show-arrows="hover"  cycle>
            <v-carousel-item
            v-for="(item, index) in recentArticles"
            :key="index"
                :src="item.img"
                    cover
                >
                <div class="text-h2">
                    {{ item.title }}
                </div>
            </v-carousel-item>
        </v-carousel>
      </v-container>
    </v-app>
</template>
<script setup>

import axios from 'axios'

const recentArticles = ref([
    {
        id:1, title:"title 01", img:'https://cdn.vuetifyjs.com/images/cards/docks.jpg'
    },
    {
        id:11, title:"title 031", img:'https://cdn.vuetifyjs.com/images/cards/hotel.jpg'
    },
    {
        id:12, title:"title 021", img:'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg'
    }
])

axios
.get("url/fre")
.then((response) => {
    //!incomment this
    //recentArticles.value= response.data
    
})
.catch((error) => {
    console.log({ error })
})

</script>
  
  