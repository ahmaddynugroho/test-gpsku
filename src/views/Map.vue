<template>
  <div class="flex flex-col min-h-screen">
    <Navbar />
    <div class="flex flex-grow">
      <div class="flex flex-col p-4 flex-grow-0 w-96">
        <!-- SEARCH -->
        <Input
          v-model="searchString"
          placeholder="Search"
          faIcon="fas fa-search text-gray-400"
          faIconOnFocus="text-blue-500"
          :faIconButton="
            isSearchStringEmpty()
              ? ''
              : 'fas fa-times text-gray-400 hover:text-blue-500'
          "
          @faIconButtonClick="searchStringClear"
        />

        <!-- TABS -->
        <ul class="flex-grow-0 grid grid-cols-3 text-gray-400">
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
        <div class="flex flex-col flex-grow">
          <!-- TAB CONTENT -->
          <ul class="flex-grow-0 h-44 overflow-auto">
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

          <!-- LEFT LOWER MENU -->
          <ul class="flex-grow">
            <div class="flex flex-col">
              <!-- TABS -->
              <ul class="flex-grow-0 grid grid-cols-2 text-gray-400">
                <li
                  class="py-2 text-center border-b-4 border-gray-300 cursor-pointer"
                  :class="{ active: isTabDetailActive('info-device') }"
                  @click="setTabDetail('info-device')"
                >
                  Info Device
                </li>
                <li
                  class="py-2 text-center border-b-4 border-gray-300 cursor-pointer"
                  :class="{ active: isTabDetailActive('kontrol') }"
                  @click="setTabDetail('kontrol')"
                >
                  Kontrol
                </li>
              </ul>

              <!-- TAB CONTENTS -->
              <ul class="">
                <li :class="{ hidden: !isTabDetailActive('kontrol') }">
                  <Button v-bind="buttonEngine" />
                </li>
              </ul>

              <!-- MENU BUTTONS -->
              <div class="flex flex-col text-gray-700 text-xs">
                <div class="flex">
                  <Button
                    title="Req Photo"
                    faIconTop="far fa-image fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                  <Button
                    title="Over Speed"
                    faIconTop="fas fa-tachometer-alt fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                  <Button
                    title="Upload"
                    faIconTop="fas fa-upload fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                </div>
                <div class="flex">
                  <Button
                    title="Set Geofence"
                    faIconTop="fas fa-chart-area fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                  <Button
                    title="Center"
                    faIconTop="fas fa-crosshairs fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                  <Button
                    title="POI"
                    faIconTop="fas fa-hand-point-up fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                </div>
                <div class="flex">
                  <Button
                    title="Playback Speed"
                    faIconTop="far fa-play-circle fa-lg mt-2 mb-1"
                    classes="text-center flex-1 h-14 rounded bg-gray-100 m-1 py-2 cursor-pointer hover:bg-gray-300"
                  />
                </div>
              </div>
            </div>
          </ul>
        </div>
      </div>
      <div class="flex flex-col w-full">
        <div class="flex-1"></div>
        <div
          class="relative mx-auto flex flex-col ring-2 ring-blue-500 rounded p-4 w-72"
        >
          <i
            class="fas fa-times-circle absolute right-0 mr-2 transform -translate-y-2 cursor-pointer"
          ></i>
          <i
            class="fas fa-ellipsis-h absolute right-0 mr-8 transform -translate-y-2 cursor-pointer"
          ></i>
          <i class="text-center fas fa-motorcycle fa-4x"></i>
          <p class="text-center font-semibold">Beat Gun</p>
          <p class="text-center font-thin text-gray-600">27/01/2021 at 10:21</p>
          <button class="w-full bg-blue-500 text-white rounded-full my-1 py-2">
            <i class="fas fa-location-arrow"></i>
            Navigate
          </button>
          <button
            class="w-full bg-yellow-500 text-white rounded-full my-1 py-2"
          >
            <i class="fas fa-street-view"></i>
            Streetview
          </button>
          <div class="my-1 relative pl-14 bg-white">
            <i class="fas fa-barcode fa-lg absolute left-0 ml-4 mt-3"></i>
            <p class="text-gray-600 text-xs">Imei</p>
            <p>8912374098234712</p>
          </div>
          <div class="my-1 relative pl-14 bg-white">
            <i
              class="fas fa-map-marker-alt fa-lg absolute left-0 ml-4 mt-3"
            ></i>
            <p class="text-sm">Cigadung, West Java, 40123, Indoneisa</p>
            <p class="text-gray-600 text-xs">
              -74.19287340192387, -87.1273460234
            </p>
          </div>
          <div class="flex text-gray-600">
            <div class="my-2 flex-1">
              <i class="ml-2 mt-1 inline fas fa-door-closed absolute"></i>
              <p class="ml-10 mt-1 text-xs text-gray-600">Closed</p>
            </div>
            <div class="my-2 flex-1">
              <i class="ml-2 mt-1 inline fas fa-video absolute"></i>
              <p class="ml-10 mt-1 text-xs text-gray-600">Off</p>
            </div>
          </div>
          <div class="flex text-gray-600">
            <div class="my-2 flex-1">
              <i class="ml-2 mt-3 inline fas fa-tachometer-alt absolute"></i>
              <p class="ml-10 text-xs text-gray-600">Speed</p>
              <p class="ml-10 text-sm text-gray-800">2 km/h</p>
            </div>
            <div class="my-2 flex-1">
              <i class="ml-2 mt-3 inline fas fa-tachometer-alt absolute"></i>
              <p class="ml-10 text-xs text-gray-600">Odometer</p>
              <p class="ml-10 text-sm text-gray-800">821.29 km/h</p>
            </div>
          </div>
          <div class="flex text-gray-600">
            <div class="my-2 flex-1"></div>
            <div class="my-2 flex-none">
              <i class="ml-2 mt-3 inline fas fa-parking absolute"></i>
              <p class="ml-10 text-xs text-gray-600">Park</p>
              <p class="ml-10 text-sm text-gray-800">12:27:34</p>
            </div>
            <div class="my-2 flex-1"></div>
          </div>
        </div>
        <div class="flex-1"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar'
import Button from '../components/UI/Button'
import Input from '../components/UI/Input'

export default {
  components: {
    Navbar,
    Button,
    Input,
  },
  data() {
    return {
      searchString: '',
      tabActive: 'all',
      tabDetailActive: 'kontrol',
      buttonEngine: {
        classes: 'bg-blue-500 rounded text-white my-2 py-2 w-full block',
        title: 'Engine On',
      },
    }
  },
  methods: {
    dropMenu2() {
      const e = document.querySelector('li#user-1 ul')
      const f = document.querySelector('li#user-1 i')
      e.classList.toggle('hidden')
      f.classList.toggle('rotate-90')
    },
    dropMenu3() {
      const g = document.querySelector('li#user-2 ul')
      const h = document.querySelector('li#user-2 i')
      g.classList.toggle('hidden')
      h.classList.toggle('rotate-90')
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
    setTabDetail(tabName) {
      this.tabDetailActive = tabName
    },
    isTabDetailActive(tabName) {
      return this.tabDetailActive === tabName
    },
  },
  mounted() {
    const e = document.querySelector('#title')
    e.text += ' | MAP'
  },
  beforeUnmount() {
    const e = document.querySelector('#title')
    e.text = e.text.slice(0, e.text.length - 6)
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
