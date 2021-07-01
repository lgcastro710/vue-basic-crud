<template>
  <nav class="" style="background: #48cdfb">
    <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
      <div class="relative flex items-center justify-between h-16">
        <button class="text-white p-4">
          <router-link to="/">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5"
              viewBox="0 0 20 20"
              fill="currentColor"
            >
              <path
                d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"
              />
            </svg>
          </router-link>
        </button>
        <div
          class="
            absolute
            inset-y-0
            right-0
            flex
            items-center
            pr-2
            sm:static
            sm:inset-auto
            sm:ml-6
            sm:pr-0
          "
        >
          <!-- aqui va el Badger -->
          <div class="flex items-center justify-center">
            <p class="mr-2 text-white text-sm">Productos</p>
            <div
              class="
                w-4
                h-4
                rounded-full
                py-2
                px-4
                flex
                items-center
                justify-center
              "
              style="background: #f47477"
            >
              <p class="text-white text-xs">
                {{ lista.length }}
              </p>
            </div>
          </div>
          <!-- Profile dropdown -->
          <div class="ml-3 relative">
            <div>
              <button
                type="button"
                class="
                  bg-gray-800
                  flex
                  text-sm
                  rounded-full
                  focus:outline-none
                  focus:ring-2
                  focus:ring-offset-2
                  focus:ring-offset-gray-800
                  focus:ring-white
                "
              >
                <img
                  class="h-8 w-8 rounded-full"
                  src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
                  alt=""
                />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Mobile menu, show/hide based on menu state. -->
    <div class="sm:hidden" id="mobile-menu">
      <div class="px-2 pt-2 pb-3 space-y-1">
        <!-- Current: "bg-gray-900 text-white", Default: "text-gray-300 hover:bg-gray-700 hover:text-white" -->
        <a
          href="#"
          class="
            bg-gray-900
            text-white
            block
            px-3
            py-2
            rounded-md
            text-base
            font-medium
          "
          aria-current="page"
          >Dashboard</a
        >

        <a
          href="#"
          class="
            text-gray-300
            hover:bg-gray-700
            hover:text-white
            block
            px-3
            py-2
            rounded-md
            text-base
            font-medium
          "
          >Team</a
        >

        <a
          href="#"
          class="
            text-gray-300
            hover:bg-gray-700
            hover:text-white
            block
            px-3
            py-2
            rounded-md
            text-base
            font-medium
          "
          >Projects</a
        >

        <a
          href="#"
          class="
            text-gray-300
            hover:bg-gray-700
            hover:text-white
            block
            px-3
            py-2
            rounded-md
            text-base
            font-medium
          "
          >Calendar</a
        >
      </div>
    </div>
  </nav>
</template>
<script>
export default {
  props: {
    lista: Array,
  },
};
</script>