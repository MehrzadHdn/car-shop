<template>
  <BaseHeader />
  <HomePage />
</template>
<script lang="ts">
import BaseHeader from "./components/BaseHeader.vue";
import HomePage from "./views/HomePage.vue";

export default {
  components: {
    BaseHeader,
  },
};
</script>

<style scoped></style>
