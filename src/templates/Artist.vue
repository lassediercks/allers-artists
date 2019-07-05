    <template>
  <Layout>
    <h1>{{$page.artist.name}}</h1>

    <img :src="$page.artist.profileimage" alt />
    <h2>data:</h2>
    <div>{{$page.artist}}</div>
  </Layout>
</template>

<page-query>

query Artist ($id: String!) {
  artist: artist (id: $id){
    name,
    id,
    profileimage,
    pictures,
    vita{
			entry{
        year,
        description
      }
    },
    bio{
      entry{
        description,
        content
      }
    },
    theater{
      entry{
        year,
        name,
        description
      }
    }
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


<style>
img {
  width: 100%;
}
</style>