<template>
  <footer>
    <div class="relative font-sans">
      <div class="flex flex-col flex-wrap px-5 py-1 text-gray-300 md:flex-row">
        <!-- <div class="flex-1 px-6 py-2">
          <img
            src="@/assets/images/logo.png"
            alt="logo Webflix"
            class="w-1/3 px-1 py-1 md:w-auto"
          />
          <div class="w-1/3 px-1 py-1 md:w-auto" />
          <p class="text-base md:text-xl">
            You can find various gnres and save them to watch later
          </p>
        </div>
        <div class="flex-1 px-6 py-2">
          <h4 class="text-xl text-white">Sitemap</h4>
          <p class="text-base md:text-xl">Home</p>
          <p class="text-base md:text-xl">Watch List</p>
        </div>
        <div class="flex-1 px-6 py-2">
          <h4 class="text-xl text-white">Official Tools</h4>
          <p class="text-base md:text-xl">Jikan.moe</p>
          <p class="text-base md:text-xl">Netlify</p>
          <p class="text-base md:text-xl">Vue</p>
        </div>
        <div class="flex-1 px-6 py-2">
          <h4 class="text-xl text-white">Support</h4>
          <p class="text-base md:text-xl">WA: 0821999999</p>
          <p class="text-base md:text-xl">Email: hello@weebfix.com</p>
          <p class="text-base md:text-xl">Selangkah.org</p>
        </div> -->
      </div>
      <ul class="flex flex-col flex-wrap px-5 py-1 text-gray-300 md:flex-row">
        <li class="flex-1 px-6 py-2">
          <img
            src="@/assets/images/logo.png"
            alt="logo Webflix"
            class="w-1/3 px-1 py-1 md:w-auto"
          />
          <div class="w-1/3 px-1 py-1 md:w-auto" />
          <p class="text-base">
            You can find various gnres and save them to watch later
          </p>
        </li>
        <li class="flex-1 px-6 py-2">
          <h4 class="text-xl text-white">Sitemap</h4>
          <router-link to="/">
            <p class="text-base">Home</p>
          </router-link>
          <router-link to="/WatchList">
            <p class="text-base">Watch List</p>
          </router-link>
        </li>
        <li class="flex-1 px-6 py-2">
          <h4 class="text-xl text-white">Official Tools</h4>
          <p class="text-base">Jikan.moe</p>
          <p class="text-base">Netlify</p>
          <p class="text-base">Vue</p>
        </li>
        <li class="flex-1 px-6 py-2">
          <h4 class="text-xl text-white">Support</h4>
          <p class="text-base">WA: 0821999999</p>
          <p class="text-base">Email: hello@weebfix.com</p>
          <p class="text-base">Selangkah.org</p>
        </li>
      </ul>
      <h4 class="py-4 font-sans text-center text-white">
        Copyright Weebflix 20222, All rights reserved
      </h4>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style></style>
