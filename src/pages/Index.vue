<template>
  <Layout>
    <ArtistTile
      v-for="artist in $page.artists.edges"
      :key="artist.node.name"
      :name="artist.node.name"
      :tags="artist.node.hashtags"
      :href="`artist/${artist.node.id}`"
      :src="artist.node.profileimage"
    ></ArtistTile>
    <h2>Über uns</h2>
  </Layout>
</template>

<script>
import ArtistTile from "../components/ArtistTile";

export default {
  components: { ArtistTile },
  metaInfo: {
    title: "Hello, world!",
    link: []
  }
};
</script>
<page-query>
query Artists {
  artists: allArtist {
    edges {
      node { 
        name,
        id,
        profileimage
        hashtags{
          tag
        }
      }
    }
  }
}
</page-query>

<style lang="postcss">
.home-links a {
  margin-right: 1rem;
}

.artist-image {
  width: 100%;
}
.artist-image_wrap {
  position: relative;
}
</style>

