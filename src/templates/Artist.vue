    <template>
  <Layout>
    <h1 class="name">{{$page.artist.name}}</h1>

    <img :src="$page.artist.profileimage" alt />
    <div class="content">
      <template v-if="$page.artist.bio != `` ">
        <h2>Steckbrief</h2>
        <ul>
          <li
            v-for="bio in $page.artist.bio"
            :key="bio.description"
          >{{bio.description}}: {{bio.content}}</li>
        </ul>
      </template>
      <template v-if="$page.artist.vita != `` ">
        <h2>Vita:</h2>
        <ul>
          <li
            v-for="vita in $page.artist.vita"
            :key="vita.description"
          >{{vita.year}}: {{vita.description}}</li>
        </ul>
      </template>
      <template v-if="$page.artist.repertoire != `` ">
        <h2>Repertoire</h2>
        <ul>
          <li
            v-for="repertoire in $page.artist.repertoire"
            :key="repertoire.description"
          >{{repertoire.year}}: {{repertoire.name}} {{repertoire.description}}</li>
        </ul>
      </template>
      <template v-if="$page.artist.videos != `` ">
        <h2>Videos:</h2>
        <ul>
          <li v-for="video in $page.artist.videos" :key="video.description">
            <a :href="video.file">{{video.description}}</a>
          </li>
        </ul>
      </template>
    </div>
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


<style scoped lang="postcss">
.name {
  padding: 0 1.5rem;
  font-size: 1.8rem;
  margin: 0;
}
h2 {
  font-weight: 500;
  padding: 0;
  margin: 0;
  margin-bottom: 0.5rem;
}
img {
  width: 100%;
  margin-bottom: 1.5em;
}
ul {
  font-size: 0.8rem;
  padding: 0;
  list-style-type: none;
  margin: 0;
  margin-bottom: 2em;
  li {
    display: inline-block;
  }
}
.content {
  padding: 0 1.5rem;
}
</style>