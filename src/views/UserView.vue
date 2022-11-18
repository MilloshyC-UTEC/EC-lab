<script>
import UserComponent from "../components/UserComponent.vue";
import spotifyAPI from "../utils/spotifyAPI";

export default {
  name: "UserView",
  data() {
    return {
      displayName: "",
      img: "",
      followers: 0,
    };
  },
  components: {
    UserComponent,
  },
  async created() {
    const userData = await spotifyAPI.getUser();
    //: implementar esto. llenar los datos del usuario
    
    this.displayName = userData.display_name;
    this.img = userData.img;
    this.followers = userData.followers;
    /*
    fetch(url).then((resp) => resp.json())
                .then((display_name) => this.displayName = display_name)
                .then((img) => this.img = img)
                .then((followers) => this.followers = followers);*/
  },
};
</script>

<template>
  <main>
    <UserComponent
      :displayName="displayName"
      :img="img"
      :followers="followers"
    />
  </main>
</template>