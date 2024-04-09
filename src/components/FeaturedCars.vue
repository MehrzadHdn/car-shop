<template>
  <div
    class="global flex justify-center items-center phone:w-full sm:max-w-11/12 md:w-3/6 lg:w-3/12"
  >
    <div
      class="border flex flex-col items-center justify-center border-shiri mx-2 my-2 bg-gray-50 rounded-md"
    >
      <div
        class="hover:scale-125 hover:transition-all ease-in-out flex justify-center items-center w-52 h-40"
      >
        <img class="" :src="Car" alt="car" />
      </div>
      <div class="common-2 border-t border-shiri px-2 py-4 bg-white">
        <p class="text-nowrap text-sm text-gray-500 font-medium">
          {{ model }}
        </p>
        <p class="text-nowrap text-sm text-gray-500 font-medium mt-2">
          Automatic
        </p>
        <div>
          <div class="bg-gray-50">
            <h2
              class="font-poppins text-nowrap text-sm text-center font-semibold border-t-2 border-b-2 border-dashed border-banafh mt-4 py-1 shadow-2xl"
            >
              <a class="text-wrap" href="#">{{ name }}</a>
            </h2>
          </div>
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
