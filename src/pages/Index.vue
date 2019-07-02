<template>
  <Layout>
    <g-image alt="Example image" src="~/favicon.png" width="135" />
    <div v-for="artists in $page.posts.edges" :key="artists.node.id">
      <h2>{{ artists.node.title }}</h2>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Hello, world!"
  }
};
</script>

<page-query>
query Posts {
  posts: allPost {
    edges {
      node { 
        title
      }
    }
  }
}
</page-query>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>

