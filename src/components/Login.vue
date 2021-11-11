<template>
  <div
    class="bg-darkgrey w-full md:max-w-md lg:max-w-full md:mx-auto md:w-1/2 xl:w-1/3 h-screen px-6 lg:px-16 xl:px-12 flex items-center justify-center"
  >
    <div class="w-full">
      <div class="flex-shrink-0">
        <a href="/" class="block">
          <img
            src="@/assets/images/logo.png"
            alt="Weebflix logo"
            class="h-8 md:h-13"
          />
        </a>
      </div>

      <h2 class="text-white text-xl md:text-2xl font-bold leading-tight my-6">
        Log in to your account
      </h2>

      <form class="mt-6">
        <div>
          <label class="block text-white mb-2 text-xs md:text-sm"
            >Email Address</label
          >
          <input
            type="email"
            name="email"
            id="email"
            placeholder="Input Your Email"
            class="w-full px-4 py-3 rounded-lg bg-gray-200 mt-2 border focus:border-primary focus:bg-white focus:outline-none font-bold"
            autofocus
            autocomplete
            required
          />
        </div>

        <div class="mt-4">
          <label class="block text-white mb-2 text-xs md:text-sm"
            >Password</label
          >
          <input
            type="password"
            name="password"
            id="password"
            placeholder="Input Your Password"
            minlength="6"
            class="w-full px-4 py-3 rounded-lg bg-gray-200 mt-2 border focus:border-primary focus:bg-white focus:outline-none font-bold"
            autocomplete
            required
          />
        </div>

        <button
          type="submit"
          class="w-full block bg-red-600 hover:bg-red-900 text-white font-semibold rounded-lg px-4 py-3 mt-8 md:mt-10"
        >
          Log In
        </button>
      </form>

      <hr class="my-5 border-gray-500 w-full" />

      <button
        type="button"
        class="w-full block bg-white hover:bg-gray-100 focus:bg-gray-100 text-gray-900 font-semibold rounded-lg px-4 py-3 border border-gray-300"
      >
        <div class="flex items-center justify-center">
          <span class="ml-4">Log in with Google</span>
        </div>
      </button>
      <p class="mt-8 text-white text-sm">
        Need an account?
        <button class="text-red-700">Create An Account</button>
      </p>
    </div>
  </div>
</template>
