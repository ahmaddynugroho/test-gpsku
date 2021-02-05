<template>
  <div class="container mx-auto flex justify-between py-4 relative">
    <div>
      <ul class="font-semibold text-gray-800 text-sm">
        <li class="inline-block mr-8 cursor-pointer">
          Master <i class="ml-1 fas fa-chevron-down fa-xs"></i>
        </li>
        <li class="inline-block mr-8 cursor-pointer">
          Report <i class="ml-1 fas fa-chevron-down fa-xs"></i>
        </li>
        <li class="inline-block mr-8 cursor-pointer">
          Billing <i class="ml-1 fas fa-chevron-down fa-xs"></i>
        </li>
        <li class="inline-block mr-8 cursor-pointer">
          HRD <i class="ml-1 fas fa-chevron-down fa-xs"></i>
        </li>
      </ul>
    </div>
    <div>
      <ul class="font-semibold text-gray-800 text-sm">
        <li class="inline-block mr-8 cursor-pointer">
          <i class="fas fa-pencil-ruler"></i>
          <i class="ml-1 fas fa-chevron-down fa-xs"></i>
        </li>
        <li class="inline-block mr-8 cursor-pointer">
          <i class="fas fa-language fa-lg"></i>
          <i class="ml-1 fas fa-chevron-down fa-xs"></i>
        </li>
        <li
          class="relative pl-5 inline-block mr-8 cursor-pointer"
          id="user"
          @click="dropMenu"
        >
          <div
            class="absolute h-6 w-6 rounded-full bg-gray-500 inline-block transform -translate-x-8"
          ></div>
          Administrator <i class="ml-1 fas fa-chevron-down fa-xs"></i>
          <ul
            class="hidden absolute rounded min-w-full right-0 transform translate-y-2"
          >
            <li class="px-4 py-2 text-gray-800 rounded hover:bg-gray-200">
              Menu numb 1
            </li>
            <li class="px-4 py-2 text-gray-800 rounded hover:bg-gray-200">
              Menu numb 2
            </li>
            <li class="px-4 py-2 text-gray-800 rounded hover:bg-gray-200">
              Menu numb 3
            </li>
          </ul>
        </li>
      </ul>
    </div>
    <div class="absolute min-w-full text-center" id="logo">GSPKU</div>
  </div>
</template>

<script>
export default {
  methods: {
    dropMenu() {
      const e = document.querySelector('li#user i')
      e.classList.toggle('transform')
      e.classList.toggle('rotate-180')

      const f = document.querySelector('li#user ul')
      f.classList.toggle('hidden')
    },
  },
}
</script>

<style scoped>
#logo {
  z-index: -1;
}
</style>
