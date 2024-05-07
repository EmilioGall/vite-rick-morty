<script>
export default {

   props: {

      charactersArray: Array,

   },

   computed: {

      percentageLoading() {

         let percentage = this.charactersArray.length * 100 / 20;

         return percentage;
         
      },

   },

};
</script>

<template>

   <h2 class="text-center">Loading...{{ percentageLoading }}%</h2>

</template>

<style scoped lang="scss"></style>