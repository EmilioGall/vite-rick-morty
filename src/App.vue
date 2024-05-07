<script>
import { store } from "./store";

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

      store,
      isLoading: false,

    };
  },

  created() {

    this.getCharacters();

  },

  methods: {

    getCharacters() {

      this.isLoading = true;

      const paramsObj = {

      };

      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
      }

      console.log("Status selected", this.store.selectedStatus);

      axios
      .get("https://rickandmortyapi.com/api/character", {
          params: paramsObj,
        })
      .then((resp) => {

        console.log(resp);

        this.store.charactersArray = resp.data.results;

        console.log("this.charactersArray", this.store.charactersArray);

        this.isLoading = false;

      });
    },
  },

};
</script>

<template>

  <div class="container-md">

    <AppHeader />

    <SelectBar @filter="getCharacters" />

    <LoadingCard v-if="isLoading" />

    <AppMain :charactersArray="store.charactersArray"  v-else />

    <!-- <h1 v-for="caracter in charactersArray"> {{ caracter.name }} </h1> -->

  </div>

</template>

<style scoped lang="scss">



</style>
