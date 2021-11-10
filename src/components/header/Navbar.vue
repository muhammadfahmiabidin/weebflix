<template>
  <div
    class="flex justify-between w-full p-4 py-5 text-white bg-transparent  md:py-6"
  >
    <router-link to="/">
      <div class="h-8">
        <img src="@/assets/images/logo.png" alt="Webflix" />
      </div>
    </router-link>
    <router-link to="/WatchList">
      <div class="flex">
        <img
          class="h-6 pr-2"
          src="@/assets/images/watch.png"
          alt="Watch List"
        />
        <p class="hidden md:block">Watch List</p>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  Name: "Navbar",
};
</script>

<style>
</style>