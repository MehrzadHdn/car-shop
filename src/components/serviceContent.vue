<template>
  <div
    class="hover:text-white hover:bg-banafh border border-gray-300 phone:my-4 phone:mx-auto lg:mx-4 lg:my-8 lg:p-8 lg:w-1/3 phone:w-5/6 rounded-md flex flex-col justify-center items-center"
  >
    <img class="w-12 h-12 my-6" :src="imgess" alt="" />

    <a class="font-poppins font-bold text-wrap mb-10" href="#">{{
      headerH1
    }}</a>
    <p
      class="font-poppins my-8 mx-12 border-b-2 border-banafh pt-5 pb-5"
    >
      ,Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut den
      fugit sed quia.
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
export default defineComponent({
  name: "serviceContent",

  setup() {},
  props: {
    imgess: {
      type: String,
      required: true,
    },
    headerH1: {
      type: String,
      required: true,
    },
  },
});
</script>

<style scoped></style>
