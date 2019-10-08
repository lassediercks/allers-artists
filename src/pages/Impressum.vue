

<template>
  <Layout>
    <h1>{{$page.site.Title}}</h1>
    <VueMarkdown>{{$page.site.content}}</VueMarkdown>
  </Layout>
</template>


<page-query>
query Impressum {
  site: site(id:"f9f0b4b5e683b80d2b20dccfa34f41a5"){
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