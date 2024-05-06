<script>
import SimpleCard from "./SimpleCard.vue";

export default {

   components: {

      SimpleCard,

   },

   props: {

      charactersArray: Array,

   },

   data() {
      return {

      };
   },

};
</script>

<template>
   
   <div class="row g-4">

      <div class="col-3" v-for="character in charactersArray">

         <SimpleCard :characterObj="character"/>

      </div>

   </div>

</template>

<style scoped lang="scss"></style>