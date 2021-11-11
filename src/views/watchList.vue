<template>
  <div class="watch-list">
    <div class="w-full px-4 my-auto h-80">
      <Navbar />
    </div>
    <Login />
  </div>
</template>

<script>
import Navbar from "@/components/header/Navbar.vue";
import Login from "@/components/Login.vue"

export default {
  name: "WatchList",
  components: {
    Navbar,
    Login,
  },
};
</script>
