<template>
  <button
    class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 border border-blue-700 rounded font-poppins"
  ><slot></slot></button>
</template>

<script lang="ts">
import {defineComponent} from "vue"
export default defineComponent({
  name: "BaseButton",
});
</script>

<style></style>
