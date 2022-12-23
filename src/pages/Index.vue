<template>
  <Layout>
    <div v-for="edge in $page.posts.edges" :key="$page.posts.id">
    <g-link :to="edge.node.path"> {{edge.node.title}} </g-link>
    </div>


  </Layout>
</template>

<page-query>
    query Post{
        posts: allPost {
          edges {
            node{
              title
              path
              content
            }
          }
        }
    }
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
