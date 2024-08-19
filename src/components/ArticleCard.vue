<template>
    <v-card
      class="mx-auto"
      max-width="344"
    >
      <v-img
        height="200px"
        :src="article.img"
        cover
      ></v-img>
  
      <v-card-title>
       {{article.title}}
      </v-card-title>
  
      <v-card-text       class="truncate-text"
      >
       {{article.content}}
      </v-card-text>
  
      <v-card-actions>
        <v-list-item link title="Explore" :to="`/article/${article.id}`"></v-list-item>
  
      </v-card-actions>
  
    </v-card>
  </template>
  <script setup>

defineProps(
    {
        article:{
            type:Object,
            default:()=>({})
        }
    }
)
</script>
<style>
.truncate-text {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}</style>
 