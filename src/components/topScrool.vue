<template>
  <button
    id="scrollToTopBtn"
    class="group fixed bottom-5 right-5 z-10 border-2 border-black rounded-full text-white bg-banafh p-4 hover:text-blue-600 transition-all"
    v-show="showButton"
    @click="scrollToTop"
  >
    <img class="w-2 h-2 4" src="/img/icons8-top-64.png" alt="" />
  </button>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from "vue";

const showButton = ref<boolean>(false);

const handleScroll = (): void => {
  //window.pageYOffset
  if (window.scrollY > 20) {
    showButton.value = true;
  } else {
    showButton.value = false;
  }
};

const scrollToTop = (): void => {
  window.scrollTo({
    top: 0,
    behavior: "smooth",
  });
};

onMounted((): void => {
  window.addEventListener("scroll", handleScroll);
});

onBeforeUnmount((): void => {
  window.removeEventListener("scroll", handleScroll);
});
</script>
