<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";
import LoadingCard from "./components/LoadingCard.vue";
import SelectBar from "./components/SelectBar.vue";

export default {

  components: {

    AppHeader,
    AppMain,
    LoadingCard,
    SelectBar,

  },

  data() {
    return {

      charactersArray: [],

    };
  },

  created() {

    axios
      .get("https://rickandmortyapi.com/api/character")
      .then((resp) => {

        console.log(resp);

        this.charactersArray = resp.data.results;

        console.log("this.charactersArray", this.charactersArray);

      });

  },

};
</script>

<template>

  <div class="container-md">

    <AppHeader />

    <SelectBar />

    <LoadingCard :charactersArray="charactersArray" v-if="charactersArray.length < 20" />

    <AppMain :charactersArray="charactersArray"  v-else />

    <!-- <h1 v-for="caracter in charactersArray"> {{ caracter.name }} </h1> -->

  </div>

</template>

<style scoped lang="scss"></style>
