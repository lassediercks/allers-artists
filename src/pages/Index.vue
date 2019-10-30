<template>
  <Layout>
    <p>{{$page.site.aboutus}}</p>

    <ArtistTile
      v-for="artist in $page.artists.edges"
      :key="artist.node.name"
      :name="artist.node.name"
      :tags="artist.node.hashtags"
      :href="`artist/${artist.node.id}`"
      :src="artist.node.profileimage"
    ></ArtistTile>
    <h2>Über uns</h2>
    {{$page.site.david}}
    <g-image :src="$page.site.davidImage" alt />
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
  artists: allArtist (sortBy: "gender", order: ASC) {
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
  site:  site(id: "3ff0627b4a78b86bb3d6ecf19a1580d1"){
    aboutus,
    david,
    davidImage
  },
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
img {
  width: 100%;
}
</style>

