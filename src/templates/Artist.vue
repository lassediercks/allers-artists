    <template>
  <Layout>
    <h1>{{$page.artist}}</h1>
  </Layout>
</template>

<page-query>

query Artist ($id: String!) {
  artist: artist (id: $id){
    name,
    id,
    pictures
  }
}
</page-query>

<script>
import Layout from "~/layouts/Default.vue";

export default {
  components: {
    Layout
  }
};
</script>
