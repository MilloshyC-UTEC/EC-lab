<script>
export default {
  name: "HomeView",
  props: ["displayName", "img", "followers"],
};
</script>

<template>
  
  <h1>Followers: {{followers}}</h1>
  <img :src="img"/>
  
  
</template>
