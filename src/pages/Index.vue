<template>
  <Layout>
    <div v-for="artist in $page.artists.edges" :key="artist.node.name">
      <a class="artist-name" :href="`artist/${artist.node.id}`">{{ artist.node.name }}</a>
      <div class="artist-image_wrap">
        <img class="artist-image" :src="artist.node.profileimage" alt />
        <div class="artist-hashtags">
          <span
            class="artist-hashtag"
            v-for="tag in artist.node.hashtags"
            :key="tag.tag"
          >#{{tag.tag}}</span>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: "Hello, world!",
    link: [
      {
        href:
          "https://fonts.googleapis.com/css?family=Abril+Fatface&display=swap",
        rel: "stylesheet"
      }
    ]
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
.artist-name {
  font-family: rollerscript-smooth, sans-serif;
  font-size: 50px;
  text-decoration: none;
  color: inherit;
}
.artist-image {
  width: 100%;
}
.artist-image_wrap {
  position: relative;
}
.artist-hashtags {
  position: absolute;
  bottom: 0;
  padding: 0 1em;
}
.artist-hashtag {
  display: inline-block;
  font-weight: bold;
  margin: 0 0.5em;
  padding: 1em;
  background: white;
}
</style>

