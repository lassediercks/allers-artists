    <template>
  <Layout>
    <h1>{{$page.artist.name}}</h1>

    <img :src="$page.artist.profileimage" alt />
    <h2>Steckbrief</h2>
    <ul>
      <li
        v-for="bio in $page.artist.bio"
        :key="bio.description"
      >{{bio.description}}: {{bio.content}}</li>
    </ul>
    <h2>Vita:</h2>
    <ul>
      <li
        v-for="vita in $page.artist.vita"
        :key="vita.description"
      >{{vita.year}}: {{vita.description}}</li>
    </ul>
    <h2>Repertoire</h2>
    <ul>
      <li
        v-for="repertoire in $page.artist.repertoire"
        :key="repertoire.description"
      >{{repertoire.year}}: {{repertoire.name}} {{repertoire.description}}</li>
    </ul>
    <h2>Videos:</h2>
    <ul>
      <li v-for="video in $page.artist.videos" :key="video.description">
        <a :href="video.file">{{video.description}}</a>
      </li>
    </ul>
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
        year,
        description
    },
    bio{
        description,
        content
    },
    repertoire{
      year,
      name, 
      description
    },
    videos{
      description,
      file
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