<template>
  <header
    class="shadow-lg fixed z-50 w-full transition-all ease-in-out duration-300 md:px-16 phone:px-7"
    :class="header_bg_custom"
  >
    <nav class="mx-auto">
      <div class="max-w-6xl mx-auto">
        <div class="flex justify-between">
          <div class="flex">
            <div class="lg:hidden flex items-center px-4 py-2">
              <button @click="handleMenuBar()" class="show-menu">
                <img
                  class="border-2 border-banafh rounded-md w-10 h-10"
                  :src="icon"
                />
              </button>
              <img src="" alt="" />
            </div>
            <div class="lg:flex lg:justify-between lg:gap-52 py-2">
              <a href="#" class="flex items-start justify-center py-2 px-2">
                <span
                  class="ml-5 lg:ml-0 font-normal font-rufina text-white text-center phone:text-xl lg:text-2xl phone:text-center"
                  >CARVILLA</span
                >
              </a>

              <div
                class="lg:items-center lg:justify-center lg:space-x-4 phone:hidden lg:flex"
              >
                <ul class="flex gap-8">
                  <li>
                    <a href="#" class="py-4 px-2 text-sm text-banafh">HOME</a>
                  </li>
                  <li>
                    <a
                      href="clients.vue"
                      class="py-4 px-2 text-white text-sm hover:text-banafh transition duration-300"
                      >SERVICE</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="py-4 px-1 text-white text-sm hover:text-banafh transition duration-300"
                      >FEATURED CARS</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="py-4 px-2 text-white text-sm hover:text-banafh transition duration-300"
                      >BRANDS</a
                    >
                  </li>
                  <li>
                    <a
                      href="#"
                      class="py-4 px-2 text-white text-sm hover:text-banafh transition duration-300"
                      >CONTACT</a
                    >
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </nav>
    <div class="hidden mobile-menu">
      <ul class="bg-black p-3">
        <li>
          <a
            href="BaseFooter.vue"
            class="block text-sm px-2 py-4 md:text-xl text-banafh hover:text-banafh font-semibold"
            >HOME</a
          >
        </li>
        <li>
          <a
            href=""
            class="block text-sm px-2 py-4 md:text-xl text-white hover:text-banafh transition duration-300"
            >SERVICE</a
          >
        </li>
        <li>
          <a
            href=""
            class="block text-sm px-2 py-4 md:text-xl text-white hover:text-banafh transition duration-300"
            >FEATURED CARS</a
          >
        </li>
        <li>
          <a
            href=""
            class="block text-sm px-2 py-4 md:text-xl text-white hover:text-banafh transition duration-300"
            >BRANDS</a
          >
        </li>
        <li>
          <a
            href=""
            class="block text-sm px-2 py-4 md:text-xl text-white hover:text-banafh transition duration-300"
            >CONTACT</a
          >
        </li>
      </ul>
    </div>
  </header>
</template>

<script lang="ts">
import { computed, defineComponent, onMounted, onUnmounted, ref } from "vue";

import BaseButton from "./BaseButton.vue";

export default defineComponent({
  name: "BaseHeader",
  components: {
    BaseButton,
  },
  setup() {
    const menuIcon = ref<boolean>(true);
    const bggg = ref<boolean | null>(null);

    function handleMenuBar() {
      menuIcon.value = !menuIcon.value;
    }
    window.addEventListener("DOMContentLoaded", () => {
      const btn = document.querySelector(".show-menu");
      const mobileMenu = document.querySelector(".mobile-menu");
      btn?.addEventListener("click", () => {
        mobileMenu?.classList.toggle("hidden");
      });
    });
    const icon = computed(() => {
      return menuIcon.value === true ? "/img/menu.svg" : "/img/cancel.svg";
    });
    // document.addEventListener("scroll", function () {
    //   if (window.scrollY > 50) {
    //     bggg.value = "bg-black  transition duration-300 ease-in-out";
    //   } else if (window.scrollY < 50) {
    //     bggg.value = "transition duration-300 ease-in-out";
    //   }
    // });

    // document.addEventListener("resize", function () {
    //   if (window.innerWidth < 1022) {
    //     bggg.value = "bg-black";
    //   } else if (window.innerWidth > 1022) {
    //     bggg.value = "";
    //   }
    //});

    const scrollAndResize = () => {
      if (window.innerWidth < 1022) bggg.value = true;
      else if (window.scrollY > 100) bggg.value = true;
      else bggg.value = false;
    };

    const header_bg_custom = computed(() => {
      return bggg.value === true
        ? "bg-black transition-all ease-in-out delay-150 duration-500 scale-110 py-3  "
        : "";
    });
    onMounted(() => {
      scrollAndResize();
      window.addEventListener("scroll", scrollAndResize);
      window.addEventListener("resize", scrollAndResize);
    });
    onUnmounted(() => {
      window.removeEventListener("scroll", scrollAndResize);
      window.removeEventListener("resize", scrollAndResize);
    });
    return {
      menuIcon,
      handleMenuBar,
      icon,
      bggg,
      header_bg_custom,
      scrollAndResize,
    };
  },
});
</script>
<style scoped>
.bg-bl {
  background-color: black;
}
</style>
