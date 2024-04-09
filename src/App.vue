<template>
  <BaseHeader />
  <HomePage />
  <topScrool />
</template>
<script lang="ts">
import BaseHeader from "./components/BaseHeader.vue";
import HomePage from "./views/HomePage.vue";
import topScrool from "./components/topScrool.vue";

export default {
  components: {
    BaseHeader,
    HomePage,
    topScrool,
  },
};
</script>

<style scoped></style>
