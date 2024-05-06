<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {

  components: {
    
    AppHeader,
    AppMain,
    
  },

  data() {
    return {

    };
  },

  created() {

    axios
      .get("https://rickandmortyapi.com/api/character")
      .then((resp) => {
        console.log(resp);
      });

  },

};
</script>

<template>

  <AppHeader />
  <AppMain />

</template>

<style scoped lang="scss">

</style>
