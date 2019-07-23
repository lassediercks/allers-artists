<template>
  <div class="wrap">
    <h2 class="name">{{name}}</h2>
    <a :href="href" class="image" :style="{backgroundImage: `url(${src})`}">
      <div class="hashtags">
        <span class="tag" v-for="tag in tags" :key="tag.tag">#{{tag.tag}}</span>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  props: ["name", "src", "tags", "href"]
};
</script>

<style scoped lang="postcss">
.wrap {
  display: flex;
  flex-direction: column;
  margin-bottom: 5em;
}
.wrap:nth-child(2n -1) {
  align-items: flex-end;
  text-align: right;
}
.name {
  padding: 0 1.5rem;
  font-size: 1.35rem;
  text-decoration: none;
  color: inherit;
  margin: 0;
}
.image {
  color: inherit;
  text-decoration: none;
  display: flex;
  align-items: flex-end;
  width: calc(100vw - 1.5rem);
  height: 10rem;
  background-size: cover;
  background-position: center center;
}
.hashtags {
  font-size: 16px;
  display: grid;
  padding: 0 1.5rem;
  grid-gap: 1em;
  grid-auto-flow: column;
}
.tag {
  padding: 0.5em 0.5em 0;
  background: white;
  line-height: 1;
}
</style>
