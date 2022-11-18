<script>
import spotifyAPI from "../utils/spotifyAPI";
import ArtistAlbumComponent from "../components/ArtistAlbumComponent.vue";

export default {
  name: "MainView",
  components: {
    ArtistAlbumComponent,
  },
  methods: {
    a() {
      return "";
    },
  },
  data() {
    return {
      albums: [],
    };
  },
  async created(id) {
    //: pass album id
    const artistAlbums = await spotifyAPI.getArtistAlbums(id);
    console.log(artistAlbums);
    this.albums = artistAlbums.items;
  },
};
</script>

<template>
  <div class="main">
    <div class="albums-container">
      {{/*TODO: Mandar los datos del album. Mira el componente para ver que se manda. Recuerda iterar porque son varios albums*/ }}
      <ArtistAlbumComponent
      ></ArtistAlbumComponent>
    </div>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .main {
    display: flex;
    max-height: 70vh;
    max-width: 70vh;
  }

  .albums-container {
    text-align: center;
    overflow-y: auto;
    vertical-align: middle;
    display: grid;
    grid-template-columns: auto auto;
    grid-gap: 10px;
    padding: 10px;
  }
}
</style>
