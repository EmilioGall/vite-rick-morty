<script>
import { store } from "../store";

export default {

   data() {
      return {

         store,

         statusArray: ["Alive", "Dead", "unknown"],

      };
   },

};
</script>

<template>

   <div class="py-4 border">

      <div class="d-flex justify-content-between align-items-center">

         <div>

            <select 
            class="form-select" 
            aria-label="Default select example"
            v-model="store.selectedStatus"
            @change="$emit('filter')">

               <option selected value="All">All</option>

               <option :value="status" v-for="status in statusArray">

                  {{ status }}

               </option>

            </select>

         </div>

         <p class="fs-2">

            {{ store.charactersArray.length }} selected characters

         </p>

      </div>

   </div>

</template>

<style scoped lang="scss"></style>