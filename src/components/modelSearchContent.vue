<template>
  <select class="" name="" id="">
    <option value=""  name="Select Year" v-for="option in options" :key="option">
        
      {{ option }}
    </option>
  </select>
</template>

<script lang="ts">
import { defineComponent, PropType } from "vue";
export default defineComponent({
  name: "modelSearchContent",
  setup() {},
  props: {
    options: {
      required: true,
      type: Array as PropType<string[]>,
    },
    name: {
      required: true,
      type: Array as PropType<string[]>,
    },
    label: {
      required: true,
      type: Array as PropType<string[]>,
    },
  },
});
</script>

<style></style>
