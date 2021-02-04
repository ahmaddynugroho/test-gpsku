<template>
  <div class="min-h-screen">
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
    <div class="flex">
      <div class="p-4 flex-grow-0">
        <div class="relative">
          <span
            class="absolute bottom-5 left-4 fas fa-search text-gray-400"
          ></span>
          <input
            class="my-2 pl-12 pr-4 py-2 rounded-md bg-gray-100 w-full focus:outline-none focus:ring-1 focus:ring-blue-500"
            type="text"
            placeholder="Search"
            id="search"
            v-model="searchString"
          />
          <button
            class="absolute bottom-5 right-4 fas fa-times text-gray-400 hover:text-gray-600"
            :class="{ hidden: isSearchStringEmpty() }"
            @click="searchStringClear"
          ></button>
        </div>
        <ul class="grid grid-cols-3 text-gray-400">
          <li
            class="py-2 text-center border-b-4 border-gray-300 cursor-pointer"
            :class="{ active: isTabActive('all') }"
            @click="setTab('all')"
          >
            All
          </li>
          <li
            class="py-2 text-center border-b-4 border-gray-300 cursor-pointer"
            :class="{ active: isTabActive('online') }"
            @click="setTab('online')"
          >
            Online
          </li>
          <li
            class="py-2 text-center border-b-4 border-gray-300 cursor-pointer"
            :class="{ active: isTabActive('offline') }"
            @click="setTab('offline')"
          >
            Offline
          </li>
        </ul>
        <div class="flex flex-col">
          <ul class="flex-grow">
            <li :class="{ hidden: !isTabActive('all') }">
              <ul>
                <li
                  class="pl-10 my-1 py-2 w-full relative cursor-pointer rounded"
                  id="user-1"
                >
                  <div
                    class="absolute h-6 w-6 rounded-full bg-gray-500 inline-block transform -translate-x-8"
                  ></div>
                  <p @click="dropMenu2">
                    User
                    <i
                      class="absolute right-0 mr-4 transform translate-y-2 fas fa-chevron-down fa-xs"
                    ></i>
                  </p>
                  <ul
                    class="hidden rounded min-w-full right-0 transform translate-y-2"
                  >
                    <li
                      class="pl-12 px-4 py-2 text-gray-800 rounded hover:bg-gray-200 relative border-b border-gray-200"
                    >
                      <i
                        class="fas fa-motorcycle fa-lg absolute left-0 ml-3 mt-4"
                      ></i>
                      <i
                        class="fas fa-wifi fa-xs absolute right-0 mr-3 mt-4"
                      ></i>
                      <p>NMAX</p>
                      <p class="text-gray-600 text-xs">
                        15/01/2021 at 15:27:17
                      </p>
                    </li>
                    <li
                      class="pl-12 px-4 py-2 text-gray-800 rounded hover:bg-gray-200 relative border-b border-gray-200"
                    >
                      <i class="fas fa-car fa-lg absolute left-0 ml-3 mt-4"></i>
                      <i
                        class="fas fa-wifi fa-xs absolute right-0 mr-3 mt-4"
                      ></i>
                      <p>Sedan</p>
                      <p class="text-gray-600 text-xs">
                        15/01/2021 at 15:27:17
                      </p>
                    </li>
                  </ul>
                </li>
                <li
                  class="pl-10 my-1 py-2 w-full relative cursor-pointer rounded"
                  id="user-2"
                >
                  <div
                    class="absolute h-6 w-6 rounded-full bg-gray-500 inline-block transform -translate-x-8"
                  ></div>
                  <p @click="dropMenu3">
                    User
                    <i
                      class="absolute right-0 mr-4 transform translate-y-2 fas fa-chevron-down fa-xs"
                    ></i>
                  </p>
                  <ul
                    class="hidden rounded min-w-full right-0 transform translate-y-2"
                  >
                    <li
                      class="pl-12 px-4 py-2 text-gray-800 rounded hover:bg-gray-200 relative border-b border-gray-200"
                    >
                      <i
                        class="fas fa-motorcycle fa-lg absolute left-0 ml-3 mt-4"
                      ></i>
                      <i
                        class="fas fa-wifi fa-xs absolute right-0 mr-3 mt-4"
                      ></i>
                      <p>NMAX</p>
                      <p class="text-gray-600 text-xs">
                        15/01/2021 at 15:27:17
                      </p>
                    </li>
                    <li
                      class="pl-12 px-4 py-2 text-gray-800 rounded hover:bg-gray-200 relative border-b border-gray-200"
                    >
                      <i class="fas fa-car fa-lg absolute left-0 ml-3 mt-4"></i>
                      <i
                        class="fas fa-wifi fa-xs absolute right-0 mr-3 mt-4"
                      ></i>
                      <p>Sedan</p>
                      <p class="text-gray-600 text-xs">
                        15/01/2021 at 15:27:17
                      </p>
                    </li>
                  </ul>
                </li>
              </ul>
            </li>
          </ul>
          <ul class="flex-grow">
            <li>content</li>
          </ul>
        </div>
      </div>
      <div class="flex-grow">map</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchString: '',
      tabActive: 'all',
    }
  },
  methods: {
    dropMenu() {
      const e = document.querySelector('li#user i')
      e.classList.toggle('transform')
      e.classList.toggle('rotate-180')

      const f = document.querySelector('li#user ul')
      f.classList.toggle('hidden')
    },
    dropMenu2() {
      const e = document.querySelector('li#user-1 ul')
      const f = document.querySelector('li#user-1 i')
      e.classList.toggle('hidden')
      f.classList.toggle('rotate-90')
    },
    dropMenu3() {
      const g = document.querySelector('li#user-2 ul')
      g.classList.toggle('hidden')
    },
    searchStringClear() {
      this.searchString = ''
    },
    isSearchStringEmpty() {
      return !(this.searchString.length > 0)
    },
    setTab(tabName) {
      this.tabActive = tabName
    },
    isTabActive(tabName) {
      return this.tabActive === tabName
    },
  },
}
</script>

<style scoped>
#logo {
  z-index: -1;
}
.active {
  @apply text-blue-500 border-blue-500;
}
</style>
