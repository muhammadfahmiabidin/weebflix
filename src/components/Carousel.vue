<template>
  <!--  ============== tambahkan ini ke views =================== -->
  <!-- slider modals -->
  <!-- <Carousel class="carousel"  v-slot="{ currentSlide }">
      <Slide v-for="(slide, index) in carouselSlide" :key="index">
        <div v-show="currentSlide === index+1" class="slide-info">
          <img :src="require(`../assets/images/${slide}.jpg`)" alt="" />
        </div>
      </Slide>
    </Carousel> -->
  <!-- ========================================================== -->

  <div class="carousel">
    <slot :currentSlide="currentSlide" />

    <!-- navigasi -->
    <div class="navigate">
      <div class="toggle-page-left">
        <i @click="prevSlide" class="fas fa-chevron-left"></i>
      </div>
      <div class="toggle-page-right">
        <i @click="nextSlide" class="fas fa-chevron-right"></i>
      </div>
    </div>

    <!-- pagination -->
    <!-- <div v-if="pagintationEnabled" class="pagination">
      <span
        @click="goToSlide(index)"
        v-for="(slide, index) in getSlideCount"
        :key="index"
        :class="{ active: index + 1 === currentSlide }"
      >
      </span>
    </div> -->
  </div>
</template>

<script>
import { ref, onMounted } from "vue";

export default {
  name: "Carousel",
  setup() {
    const currentSlide = ref(1);
    const getSlideCount = ref(null);

    // next slide
    const nextSlide = () => {
      if (currentSlide.value === getSlideCount.value) {
        currentSlide.value = 1;
        return;
      }
      currentSlide.value += 1;
    };

    // prev slide
    const prevSlide = () => {
      if (currentSlide.value === 1) {
        currentSlide.value = 1;
        return;
      }
      currentSlide.value -= 1;
    };

    onMounted(() => {
      getSlideCount.value = document.querySelectorAll(".slide").length;
      console.log(getSlideCount.value);
    });
    return { currentSlide, nextSlide, prevSlide, getSlideCount };
  },

  // ============== masukan setup pada views ini ===========
  // setup() {
  //   const carouselSlide = ["black-clover", "nanatsuno", "kimetsu"];
  //   return { carouselSlide };
  // },
};
</script>

<style lang="scss">
.navigate {
  padding: 0 16px;
  height: 100%;
  width: 100%;
  position: absolute;
  display: flex;
  justify-content: space-between;
  align-items: center;
  .toggle-page {
    display: flex;
    flex: 1;
  }
  i {
    cursor: pointer;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    background-color: #6347c7;
    color: #fff;
  }
}
.pagination {
  position: absolute;
  bottom: 24px;
  width: 100%;
  display: flex;
  gap: 16px;
  justify-content: center;
  align-items: center;
  span {
    cursor: pointer;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background-color: #fff;
    box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
  }
  .active {
    background-color: #6347c7;
  }
}

// ============ taruh css ini pada viws ===============
// .carousel {
//   position: relative;
//   max-height: 100vh;
//   height: 100vh;
//   .slide-info {
//     position: absolute;
//     top: 0;
//     left: 0;
//     width: 100%;
//     max-height: 100%;
//     height: 100%;
//     img {
//       min-width: 100%;
//       height: 100%;
//       object-fit: cover;
//     }
//   }
// }
</style>
