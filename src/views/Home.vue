<template>
  <div class="home">
    <!-- <Slider /> -->
    <div class="relative w-full my-auto bg-image h-96">
      <div class="absolute z-20 w-full my-auto bg-gray-800 bg-opacity-75 h-96">
        <div class="absolute z-30 w-full px-4 my-auto h-96">
          <Navbar class="py-4" />
          <Search />
        </div>
        <Card />
        <Detail />
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

import Detail from "../components/content/Detail.vue";
import Card from "../components/content/Card.vue";
import Navbar from "../components/header/Navbar.vue";
import Search from "../components/header/Search.vue";
import Footer from "../components/footer/Footer.vue";

export default {
  name: "Home",
  components: {
    Detail,
    Card,
    Navbar,
    Search,
    Footer,
  },
};
</script>

<style lang="scss">
.bg-image {
  background: url("../assets/images/bg.jpg");
}
</style>