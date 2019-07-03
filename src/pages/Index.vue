<template>
  <Layout>
    <div v-for="artist in $page.artists.edges" :key="artist.node.name">
      <a :href="`artist/${artist.node.id}`">{{ artist.node.name }}</a>
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
query Artists {
  artists: allArtist {
    edges {
      node { 
        name
        id
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

