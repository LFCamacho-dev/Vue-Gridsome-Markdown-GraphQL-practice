<script setup>
import Ad from '@/components/Ad.vue'

</script>

<page-query>
    query Post($id: ID!) {
        post(id: $id) {
          title
          author
          created_at
          tags {
            id
            color
            path
          }
        }
    }
</page-query>

<template>
  <div style="margin:0 auto; max-width: 700px;">

    <h1>{{ $page.post.title }}</h1>
    <p><strong>Author: </strong>{{ $page.post.author }}</p>
    <p><strong>Date Created: </strong><em>{{ $page.post.created_at }}</em></p>
    
    <br />
    <strong>Tags: </strong>
    <span
      v-for="tag in $page.post.tags"
      :key="tag.id"
      :style="`background-color: ${tag.color}; border-radius:25px; padding: 0 5px; font-size: 12px; margin: 0 2px`"
      >
      <g-link :to="tag.path" class="tag">
      {{ tag.id }} 
      </g-link>
      </span>

    <hr>

    <VueRemarkContent>
        <template v-slot:ad>
            <Ad />
        </template>
    </VueRemarkContent>
  
  </div>
</template>

<style>

    .tag{
        color: white !important;
    }
</style>


