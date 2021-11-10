<template>
  <div class="relative w-full px-4 pt-48">
    <!-- <div class="inline-flex w-auto"> -->
    <div class="pt-28">
      <h3 class="px-4 pb-2 text-xl text-white ">Upcoming</h3>
      <Carousel
        class="text-left"
        :settings="settings"
        :breakpoints="breakpoints"
        :wrap-around="false"
      >
        <Slide v-for="anime in animes" :key="anime.id">
          <div class="px-4 carousel__item">
            <div class="w-60 card">
              <div class="head-card">
                <img
                  :src="anime.movie_banner"
                  alt="Judul Anime"
                  class="h-32 w-60 rounded-2xl"
                />
              </div>
              <div class="bg-transparent body-card">
                <div class="flex flex-row flex-wrap">
                  <div class="w-3/4 py-1 pr-1">
                    <div class="bg-transparent">
                      <h2 class="text-white">{{ anime.title }}</h2>
                      <button class="px-1 text-xs bg-red-500 rounded-lg">
                        Action
                      </button>
                      <button class="px-1 text-xs bg-red-500 rounded-lg">
                        Adventure
                      </button>
                      <button class="px-1 text-xs bg-red-500 rounded-lg">
                        Fantasy
                      </button>
                      <h2 class="text-white">
                        Start Date: {{ anime.release_date }}
                      </h2>
                    </div>
                  </div>
                  <div class="w-1/4 py-1 pl-2">
                    <div class="pr-4 text-right bg-transparent">
                      <button class="px-1 text-xs bg-yellow-300 rounded-md">
                        TV
                      </button>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </Slide>

        <template #addons="{ slidesCount }">
          <Navigation
            class="text-white bg-gray-700 opacity-50"
            v-if="slidesCount > 5"
          />
        </template>
      </Carousel>
    </div>
    <!-- </div> -->
  </div>
</template>

<script>
/* eslint-disable */

import { defineComponent } from "vue";
import { Carousel, Navigation, Slide } from "vue3-carousel";

import "vue3-carousel/dist/carousel.css";
import axios from "axios";

export default defineComponent({
  name: "Card",
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data: function() {
    return {
      animes: [],
      // carousel settings
      settings: {
        itemsToShow: 1,
        snapAlign: "start",
      },
      breakpoints: {
        360: {
          itemsToShow: 1.25,
          snapAlign: "start",
        },
        410: {
          itemsToShow: 1.5,
          snapAlign: "start",
        },
        480: {
          itemsToShow: 1.75,
          snapAlign: "start",
        },
        550: {
          itemsToShow: 2,
          snapAlign: "start",
        },
        640: {
          itemsToShow: 2.25,
          snapAlign: "start",
        },
        670: {
          itemsToShow: 2.5,
          snapAlign: "start",
        },
        700: {
          itemsToShow: 2.75,
          snapAlign: "start",
        },
        850: {
          itemsToShow: 3,
          snapAlign: "start",
        },
        900: {
          itemsToShow: 3.25,
          snapAlign: "start",
        },
        970: {
          itemsToShow: 3.5,
          snapAlign: "start",
        },
        1030: {
          itemsToShow: 4,
          snapAlign: "start",
        },
        1150: {
          itemsToShow: 4.25,
          snapAlign: "start",
        },
        1250: {
          itemsToShow: 4.5,
          snapAlign: "start",
        },
        1350: {
          itemsToShow: 5,
          snapAlign: "center",
        },
        1450: {
          itemsToShow: 5.5,
          snapAlign: "start",
        },
        1600: {
          itemsToShow: 6,
          snapAlign: "center",
        },
      },
    };
  },
  methods: {
    getListAnime() {
      axios
        .get("https://ghibliapi.herokuapp.com/films")
        .then((res) => {
          this.animes = res.data; //respon dari rest api dimasukan ke users
          console.log(res.data);
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
  mounted() {
    this.getListAnime();
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
