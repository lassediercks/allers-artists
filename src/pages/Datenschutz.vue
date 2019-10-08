<template>
  <Layout>
    <h1>{{$page.site.Title}}</h1>
    <VueMarkdown>{{$page.site.content}}</VueMarkdown>
  </Layout>
</template>


<page-query>
query Datenschutz {
  site: site(id:"ddf7fdcedbbb56586a30ad7a7ea8a78d"){
    Title,
    content
  }
}
</page-query>
<script>
import VueMarkdown from "vue-markdown";

export default {
  components: { VueMarkdown }
};
</script>

<style>
</style>