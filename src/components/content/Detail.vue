<template>
  <div class="relative px-4 py-0.5 w-auto">
    <Carousel
      class="text-left"
      :settings="settings"
      :breakpoints="breakpoints"
      :wrap-around="false"
    >
      <Slide v-for="slide in 10" :key="slide">
        <div class="pcarousel__item">
          <div class="relative pt-10">
            <div class="card h-72">
              <div class="absolute head-card">
                <img
                  src="@/assets/images/black-clover-potrait.jpg"
                  alt="Detail Episode"
                  class="w-48 h-64 rounded-lg"
                />
              </div>
              <div
                class="relative h-32 px-2 bg-black rounded-b-lg opacity-70 top-32 w-44"
              >
                <p class="pt-4 text-xs text-white">Summer 2022</p>
                <p class="pt-1 text-white">Black Clover</p>
                <p class="pt-1 pb-3 text-xs text-white">Eps : {{slide}}</p>
                <button class="w-full text-sm text-white border-2 rounded-md">
                  <h4>View Detail</h4>
                </button>
              </div>
            </div>
          </div>
        </div>
      </Slide>

      <template #addons="{ slidesCount }">
        <Navigation
          class="text-white bg-gray-700 opacity-50"
          v-if="slidesCount > 1"
        />
      </template>
    </Carousel>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";

export default defineComponent({
  name: "Detail",
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data: () => ({
    // carousel settings
    settings: {
      itemsToShow: 1.5,
      snapAlign: "start",
    },
    // breakpoints are mobile first
    // any settings not specified will fallback to the carousel settings
    breakpoints: {
      360: {
        itemsToShow: 1.75,
        snapAlign: "start",
      },
      410: {
        itemsToShow: 2,
        snapAlign: "start",
      },
      480: {
        itemsToShow: 2.5,
        snapAlign: "start",
      },
      550: {
        itemsToShow: 2.75,
        snapAlign: "start",
      },
      640: {
        itemsToShow: 3,
        snapAlign: "start",
      },
      670: {
        itemsToShow: 3.5,
        snapAlign: "start",
      },
      750: {
        itemsToShow: 3.75,
        snapAlign: "start",
      },
      800: {
        itemsToShow: 4,
        snapAlign: "start",
      },
      850: {
        itemsToShow: 4.25,
        snapAlign: "start",
      },
      900: {
        itemsToShow: 4.5,
        snapAlign: "start",
      },
      980: {
        itemsToShow: 5,
        snapAlign: "start",
      },
      1030: {
        itemsToShow: 5.25,
        snapAlign: "center",
      },

      1140: {
        itemsToShow: 5.5,
        snapAlign: "start",
      },
      1250: {
        itemsToShow: 5.75,
        snapAlign: "start",
      },
      1300: {
        itemsToShow: 6,
        snapAlign: "center",
      },
      1400: {
        itemsToShow: 7,
        snapAlign: "start",
      },
      1600: {
        itemsToShow: 8,
        snapAlign: "start",
      },
    },
  }),
  methods: {
    getListAnime() {
      this.axios
        .get("https://ghibliapi.herokuapp.com/films")
        .then((Response) => {
          console.log(Response.data);
        })
        .catch((error) => console.error(error));
    },
  },
});
</script>

<style lang="scss">
.carousel__item {
  display: flex;
  justify-content: center;
  align-items: center;

  .carousel__prev,
  .carousel__next {
    box-sizing: content-box;
  }
}
</style>