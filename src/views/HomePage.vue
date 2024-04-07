<template>
  <section
    class="flex justify-center items-center background-car bg-auto sm:bg-cover lg:bg-auto xl:bg-cover flex-col welcome-hero"
  >
    <div class="z-10">
      <div class="flex justify-center flex-col items-center">
        <h1
          class="text-white text-3xl font-semibold font-poppins lg:text-center w-2/3 lg:w-full text-center mb-20 mt-20"
        >
          GET YOUR DESIRED CAR IN RESONABLE PRICE
        </h1>

        <p
          class="text-white text-sm lg:text-lg lg:text-center w-2/3 text-center mb-20 border-b-2 border-banafh pb-8"
        >
          Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </p>
        <BaseButton class="py-4 md:w-1/2 lg:w-1/6 rounded-md bg-banafh">
          contact us
        </BaseButton>
      </div>
    </div>
  </section>
  <div class="">
    <section
      id="model-search-content"
      class="shadow-2xl bg-white md:container md:mx-auto p-4 border rounded-md my-10"
    >
      <form action="#" class=" ">
        <div
          class="mt-4 mb-4 flex justify-around items-center mx-auto phone:p-4 lg:flex-row"
        >
          <div class="w-full lg:flex justify-around items-center">
            <!-- ..1.. -->
            <div
              class="col-1 w-full lg:w-1/4 lg:flex lg:flex-col lg:justify-end lg:items-center"
            >
              <div class="lg:flex lg:flex-col lg:items-center lg:w-5/12">
                <label class="font-poppins md:w-full text-nowrap" for="year"
                  >select year</label
                >
                <modelSearchContent
                  class="font-poppins rounded border phone:w-full text-gray-400 py-2 px-2 bg-gray-100 mb-6 mt-3"
                  name="year"
                  :options="optionYear"
                />
              </div>

              <div class="lg:flex lg:flex-col lg:items-center lg:w-5/12">
                <label class="font-poppins md:w-full" for="style"
                  >Body style
                </label>
                <modelSearchContent
                  class="font-poppins rounded border phone:w-full text-gray-400 py-2 px-2 bg-slate-100 mb-6 mt-3"
                  name="style"
                  :options="optionStyle"
                />
              </div>
            </div>
            <!-- ..2.. -->
            <div
              class="col-2 w-full lg:w-1/4 lg:flex lg:flex-col lg:justify-end lg:items-center"
            >
              <div class="lg:flex lg:flex-col lg:items-center lg:w-5/12">
                <label class="font-poppins md:w-full text-nowrap" for="Make"
                  >Select Make</label
                >
                <modelSearchContent
                  class="font-poppins rounded border phone:w-full text-gray-400 py-2 px-2 bg-slate-100 mb-6 mt-3"
                  name="Make"
                  :options="optionMake"
                />
              </div>
              <div class="lg:flex lg:flex-col lg:items-center lg:w-5/12">
                <label class="font-poppins md:w-full text-nowrap" for="Car"
                  >Car Condition</label
                >
                <modelSearchContent
                  class="font-poppins rounded border phone:w-full text-gray-400 py-2 px-2 bg-slate-100 mb-6 mt-3"
                  name="Car"
                  :options="optionCondition"
                />
              </div>
            </div>
            <!-- ..3.. -->
            <div
              class="col-3 w-full lg:w-1/4 lg:flex lg:flex-col lg:justify-end lg:items-center"
            >
              <div class="lg:flex lg:flex-col lg:items-center lg:w-5/12">
                <label class="font-poppins text-nowrap md:w-full" for="Model"
                  >Select Model</label
                >
                <modelSearchContent
                  class="font-poppins rounded border phone:w-full text-gray-400 py-2 px-2 bg-slate-100 mb-6 mt-3"
                  name="Model"
                  :options="optionModel"
                />
              </div>
              <div class="lg:flex lg:flex-col lg:items-center lg:w-5/12">
                <label class="font-poppins md:w-full text-wrap" for="Price"
                  >Select Price</label
                >
                <modelSearchContent
                  class="font-poppins rounded border phone:w-full text-gray-400 py-2 px-2 bg-slate-100 mb-6 mt-3"
                  name="Price"
                  :options="optionPrice"
                />
              </div>
            </div>
            <div
              class="col-4 w-full lg:w-1/4 phone:flex phone:justify-center phone:items-center phone:mt-8 lg:mt-0"
            >
              <BaseButton
                class="px-8 py-4 md:w-1/2 bg-banafh border-banafh border-0"
              >
                search
              </BaseButton>
            </div>
          </div>
        </div>
      </form>
    </section>
  </div>
  <section class="lg:flex lg:container lg:mx-auto">
    <serviceContent
      headerH1="largest dealership of car"
      imgess="/img/icons8-car-64.png"
    ></serviceContent>
    <serviceContent
      headerH1="unlimited repair warrenty"
      imgess="/img/icons8-car-repair-64.png"
    >
    </serviceContent>
    <serviceContent
      headerH1="insurence support"
      imgess="/img/icons8-car-insurance-80 (1).png"
    >
    </serviceContent>
  </section>

  <section>
    <div class="bg-gray-100">
      <div class="flex flex-col justify-center items-center mb-14">
        <p class="font-poppins font-medium text-sm pb-2">
          Checkout the Featured Cars
        </p>
        <h2
          class="section-header relative pb-4 font-poppins font-extrabold text-2xl"
        >
          Newest Cars
        </h2>
      </div>
      <div class="container mx-auto flex overflow-hidden cursor-pointer">
        <NewestCars
          :style="`transform: translateX(-${currentIndex * 100}% )`"
          v-for="item in newestcars"
          :key="item.name"
          :NewestCarsCarImg="item.img"
          :NewestCarsNameCar="item.name"
          :NewestCarsDescription="item.description"
          :NewestCarsParghraf="item.parghraf"
          @touchstart="handleTouchStart"
          @touchmove="handleTouchMove"
          @touchend="handleTouchEnd"
          @mousedown="handleMouseDown"
          @mousemove="handleMouseMove"
          @mouseup="handleMouseUp"
        ></NewestCars>
      </div>
      <div class="dots flex justify-center items-center">
        <button
          class="dot bg-white border-2 border-black px-1 py-1 rounded-full my-2 mx-1"
          v-for="item in newestcars.length"
          :key="item"
          @click="showslide"
        ></button>
      </div>
    </div>
  </section>

  <section class="Featured-Cars my-10">
    <div class="flex flex-col justify-center items-center mb-14">
      <p class="font-poppins font-medium text-sm pb-2">
        Checkout the Featured Cars
      </p>
      <h2
        class="section-header relative pb-4 font-poppins font-extrabold text-2xl"
      >
        Featured Cars
      </h2>
    </div>

    <div class="container w-full mx-auto  flex flex-row flex-g flex-wrap ">
      <FeaturedCars
        v-for="productsCar in productsCars"
        :key="productsCar.name"
        :Car="productsCar.imgCar"
        :name="productsCar.name"
        :price="productsCar.price"
        :model="productsCar.model"
        :description="productsCar.description"
      >
      </FeaturedCars>
    </div>
  </section>
  <section>
    <brandCars></brandCars>
  </section>
  <section class="footer">
    <BaseFooter />
  </section>
</template>

<script lang="ts">
import { defineComponent, reactive, ref } from "vue";
import modelSearchContent from "../components/modelSearchContent.vue";
import BaseButton from "../components/BaseButton.vue";
import serviceContent from "../components/serviceContent.vue";
import NewestCars from "../components/NewestCars.vue";
import BaseFooter from "../components/BaseFooter.vue";
import FeaturedCars from "../components/FeaturedCars.vue";
import brandCars from "../components/brandCars.vue";

export default defineComponent({
  name: "HomePage",
  components: {
    modelSearchContent,
    BaseButton,
    serviceContent,
    NewestCars,
    BaseFooter,
    FeaturedCars,
    brandCars,
  },
  setup() {
    const optionYear = reactive<string[]>(["2022", "2023", "2024"]);
    const optionStyle = reactive<string[]>(["sedan", "van", "roadster"]);
    const optionMake = reactive<string[]>(["Bmw", "benz", "dodge"]);
    const optionCondition = reactive<string[]>([
      "something",
      "something",
      "something",
    ]);
    const optionModel = reactive<string[]>(["x-7", "kia-rio", "Ford"]);
    const optionPrice = reactive<string[]>(["20.00", "$15.00", "$10.00"]);
    // ..................
    const productsCars = [
      {
        imgCar: "/img/fc1.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "BMW 6-Series Gran Coupe",
        price: "90.00",
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/ford.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "Chevrolet Camaro WMV20",
        price: 60.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/lambo.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "Lamborghini V520",
        price: 120.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/audi.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "Audi A3 Sedan",
        price: 95.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/fc8.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "BMW Xseries-6",
        price: 75.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/fc7.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "BMW 8-Series Coupe",
        price: 55.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/fc5.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "Porsche 718 Cayman",
        price: 50.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
      {
        imgCar: "/img/audi.png",
        model: "Model: 2017 3100 Mi 240HP",
        name: "Infiniti Z5",
        price: 35.0,
        description:
          "Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non.",
      },
    ];
    const newestcars = [
      {
        img: "img/ncm1.png",
        name: "chevrolet camaro za100",
        description:
          "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        parghraf:
          "Sed ut pers unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.",
      },
      {
        img: "img/ncm2.png",
        name: "BMW series-3 wagon",
        description:
          "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        parghraf:
          "Sed ut pers unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.",
      },
      {
        img: "img/ncm3.png",
        name: "ferrari 488 superfast",
        description:
          "Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        parghraf:
          "Sed ut pers unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.",
      },
    ];
    const currentIndex = ref<number>(0);
    function showslide() {
      currentIndex.value = (currentIndex.value + 1) % newestcars.length;
    }

    const touchStartX = ref<number>(0);
    const touchMoveX = ref<number>(0);
    function next() {
      currentIndex.value = (currentIndex.value + 1) % newestcars.length;
    }

    function prev() {
      currentIndex.value =
        (currentIndex.value - 1 + newestcars.length) % newestcars.length;
    }

    function handleTouchStart(event: TouchEvent) {
      touchStartX.value = event.touches[0].clientX;
    }

    function handleTouchMove(event: TouchEvent) {
      touchMoveX.value = event.touches[0].clientX;
    }

    function handleTouchEnd() {
      const deltaX = touchMoveX.value - touchStartX.value;
      if (deltaX > 50) {
        prev();
      } else if (deltaX < -50) {
        next();
      }
      touchStartX.value = 0;
      touchMoveX.value = 0;
    }

    const startDragX = ref<number>(0);
    const endDragX = ref<number>(0);
    function handleMouseDown(event: MouseEvent) {
      startDragX.value = event.clientX;
    }

    function handleMouseMove(event: MouseEvent) {
      endDragX.value = event.clientX;
    }

    function handleMouseUp() {
      const deltaX = endDragX.value - startDragX.value;
      if (deltaX > 50) {
        prev();
      } else if (deltaX < -50) {
        next();
      }
      startDragX.value = 0;
      endDragX.value = 0;
    }

    return {
      optionYear,
      optionStyle,
      optionMake,
      optionCondition,
      optionModel,
      optionPrice,
      productsCars,
      newestcars,
      showslide,
      currentIndex,
      handleTouchStart,
      handleTouchMove,
      handleTouchEnd,
      handleMouseDown,
      handleMouseMove,
      handleMouseUp,
    };
  },
});
</script>

<style>
.welcome-hero::before {
  position: absolute;
  content: "";
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(42, 45, 84, 0.6);
  z-index: 1;
}
.background-car {
  padding: 12%;
  position: relative;
  background: url("../assets/imgs/car.jpg") no-repeat;
  background-size: cover;
  background-position: center;
  background-size: cover;
  width: 100%;
}
.section-header:before {
  position: absolute;
  content: "";
  width: 80px;
  height: 2px;
  bottom: 0;

  left: 50%;
  margin-left: -42px;
  background: #4e4ffa;
}
</style>
