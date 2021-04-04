<template>
  <div class="bg-gray-900">
    <div
      class="px-4 py-5 mx-auto sm:max-w-xl md:max-w-full lg:max-w-screen-xl md:px-24 lg:px-8"
    >
      <div class="relative flex grid items-center grid-cols-2 lg:grid-cols-3">
        <ul class="flex items-center hidden space-x-8 lg:flex">
          <li>
            <a
              href="/"
              aria-label="Our product"
              title="Our product"
              class="font-medium tracking-wide text-gray-100 transition-colors duration-200 hover:text-yellow-700"
              >Product</a
            >
          </li>
          <li>
            <router-link to="/profile"
              class="font-medium tracking-wide text-gray-100 transition-colors duration-200 hover:text-yellow-700"
              >Profile</router-link
            >
          </li>
          <li>
            <a
              href="https://github.com/Chartchaloemtepa"
              aria-label="Product pricing"
              title="Product pricing"
              class="font-medium tracking-wide text-gray-100 transition-colors duration-200 hover:text-yellow-700"
              >Github</a
            >
          </li>
        </ul>
        <a
          href=""
          aria-label="Company"
          title="Company"
          class="inline-flex items-center lg:mx-auto"
        >
        <img src="~/assets/bathrobe.png" alt="" class="w-10">
          <span
            class="ml-2 text-xl font-bold tracking-wide text-gray-100 hover:text-yellow-700"
            >PP Spa</span
          >
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false,
    };
  },
};
</script>