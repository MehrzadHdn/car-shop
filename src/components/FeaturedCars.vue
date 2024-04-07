<template>
  <div class="global flex justify-center items-center lg:w-3/12  ">
    <div
      class="border flex flex-col items-center justify-center border-shiri   md:w-5/6 bg-gray-200 shadow-2xl rounded-md"
    >
    <div class=" flex justify-center items-center py-8 ">

      <img class="w-3/4 h-3/4" :src="Car"  alt="" />
    </div>
      <div class="common-2 border-t border-shiri px-2 py-4 bg-white">
        <p class="text-nowrap text-sm text-gray-500 font-medium">
          {{ model }}
        </p>
        <p class="text-nowrap text-sm text-gray-500 font-medium mt-2">
          Automatic
        </p>
        <div>
          <h2
            class="font-poppins text-nowrap text-center border-t-2 border-b-2 border-dashed border-banafh mt-4 py-2 shadow-2xl"
          >
            <a href="#">{{ name }}</a>
          </h2>
          <h3 class="font-poppins mt-2">${{ price }}</h3>
          <p class="text-gray-500 text-wrap text-start">
            {{ description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";

export default defineComponent({
  props: {
    Car: {
      type: Object as PropType<string>,
      required: true,
    },
    name: {
      type: Object as PropType<string>,
      required: true,
    },
    price: {
      type: Object as PropType<number>,
      required: true,
    },
    model: {
      type: Object as PropType<string>,
      required: true,
    },
    description: {
      type: Object as PropType<string>,
      required: true,
    },
  },
});
</script>

<style scoped></style>
