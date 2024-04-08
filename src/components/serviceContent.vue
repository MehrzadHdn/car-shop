<template>
  <div
    class="group hover:bg-banafh border border-gray-300 phone:my-4 phone:mx-auto lg:mx-4 lg:my-8 lg:p-8 lg:w-1/3 phone:w-4/5 md:w-2/4 rounded-md flex flex-col justify-center items-center"
  >
    <img class="w-12 h-12 my-6" :src="imgess"/>

    <a
      class="font-poppins font-bold text-wrap phone:px-6 text-center mb-10 group-hover:text-white"
      href="#"
      >{{ headerH1 }}</a
    >
    <p
      class="font-poppins my-8 mx-12 border-b-2 group-hover:text-white group-hover:border-white border-banafh px-4 text-center text-wrap   pb-5"
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
