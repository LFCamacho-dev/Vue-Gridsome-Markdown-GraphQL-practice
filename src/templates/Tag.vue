<script setup>

</script>

<page-query>
    query Tag($id:ID!){
        tag(id:$id){
          id
          belongsTo {
            edges{
              node{
                ... on Post {
                  title
                  path
                }
              }
            }
          }
        }
    }
</page-query>


<template>
  <div style="margin:0 auto; max-width: 700px;">
    <h3><em>Tag: {{ $page.tag.id }}</em></h3>

    <div v-for="edge in $page.tag.belongsTo.edges" :key="edge.node.id" >

    <g-link :to="edge.node.path">{{ edge.node.title }}</g-link>
    
    </div>


    <!-- <VueRemarkContent /> -->
   
  </div>
</template>


