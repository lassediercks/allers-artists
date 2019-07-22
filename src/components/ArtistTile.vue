<template>
  <div>
    <h2 class="name">{{name}}</h2>
    <a :href="href" class="image" :style="{backgroundImage: `url(${src})`}"></a>
    <span class="artist-hashtag" v-for="tag in tags" :key="tag.tag">#{{tag.tag}}</span>
  </div>
</template>

<script>
export default {
  props: ["name", "src", "tags", "href"]
};
</script>

<style scoped lang="postcss">
.name {
  font-family: var(--artist-name-font);
  font-size: 20px;
  text-decoration: none;
  color: inherit;
}
.image {
  display: block;
  max-width: 400px;
  max-height: 400px;
  width: 70vw;
  height: 70vw;
  background-size: cover;
}
.artist-hashtags {
  position: absolute;
  bottom: 0;
  padding: 0 1em;
}
</style>
