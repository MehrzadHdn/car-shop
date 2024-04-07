<template>
  <div
    class="images flex justify-center grow-0 shrink-0 items-center w-full overflow-hidden"
  >
    <div class="w-1/2"><img :src="NewestCarsCarImg" alt="" /></div>
    <div class="w-1/3 flex flex-col items-start justify-center">
      <h2 class="font-poppins text-2xl font-semibold mb-6">
        <a href="#">{{ NewestCarsNameCar }}</a>
      </h2>
      <p class="font-poppins text-gray-400 mb-8">
        {{ NewestCarsDescription }}
      </p>
      <p class="font-poppins text-gray-400 mb-8">
        Sed ut pers unde omnis iste natus error sit voluptatem accusantium
        doloremque laudantium.
      </p>
      <BaseButton class="mb-8 bg-botton font-medium py-3 px-6">
        view details
      </BaseButton>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
import BaseButton from "../components/BaseButton.vue";
export default defineComponent({
  components: {
    BaseButton,
  },
  props: {
    NewestCarsCarImg: {
      type: Object as PropType<string>,
      required: true,
    },
    NewestCarsNameCar: {
      type: Object as PropType<string>,
      required: true,
    },
    NewestCarsDescription: {
      type: Object as PropType<string>,
      required: true,
    },
    NewestCarsParghraf: {
      type: Object as PropType<string>,
      required: true,
    },
  },
});
</script>

<style></style>
