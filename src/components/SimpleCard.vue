<script>
export default {

  props: {

    characterObj: Object,

  },

  computed: {

    classObject() {
      return {

        'text-danger': this.characterObj.status === "Dead",

        'text-success': this.characterObj.status === "Alive",

        'text-secondary': this.characterObj.status === "unknown",

      }
    },

  },

};
</script>

<template>

  <div class="ms-card">

    <img :src="characterObj.image" class="ms-card-img mb-3" :alt="characterObj.name">

    <div class="ms-card-body">

      <h5 class="ms-card-title fs-4"> {{ characterObj.name }} </h5>

      <p class="fs-6 mb-1"> {{ characterObj.species }} </p>

      <p class="fs-6 mb-1" :class="classObject"> {{ characterObj.status }} </p>

    </div>

  </div>

</template>

<style scoped lang="scss">
.ms-card {

  .ms-card-img {
    border-radius: 50%;
    box-shadow: 10px 10px 30px grey;

  }

  .ms-card-body {
    text-align: center;

    .ms-card-title {}

  }

}
</style>