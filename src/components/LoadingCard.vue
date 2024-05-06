<script>
export default {

   props: {

      charactersArray: Array,

   },

   computed: {

      percentageLoading() {

         let percentage = this.charactersArray.length;

         return percentage;
         
      },

   },

};
</script>

<template>

   <h2 class="text-center">Loading...{{ percentageLoading }}%</h2>

</template>

<style scoped lang="scss"></style>