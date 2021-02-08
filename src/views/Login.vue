<template>
  <div class="container mx-auto p-4 grid grid-cols-3 gap-8">
    <!-- HEADER -->
    <div class="col-span-2"></div>
    <div class="text-xl text-gray-800 tracking-wide">GPSKU</div>

    <!-- CAROUSEL/LEFT PART -->
    <div
      class="col-span-2 ml-0 m-8 p-4 rounded-3xl bg-gray-100 text-gray-400 tracking-wide"
    >
      Carousel
    </div>

    <!-- LOGIN/RIGHT PART -->
    <div>
      <p class="text-4xl mb-6 font-semibold text-gray-800">Login</p>
      <Input v-bind="inputEmail" />

      <Input v-bind="inputPassword" @faIconButtonClick="loginPasswordReveal" />

      <div class="my-4 mx-2 flex items-center">
        <div
          class="ring-2 ring-blue-500 border-2 border-white h-4 w-4 rounded-full bg-blue-500 cursor-pointer"
          id="loginRemember"
          @click="loginRememberToggle"
        ></div>
        <span class="ml-2">Ingat saya</span>
      </div>

      <button
        class="w-full p-2 border border-blue-500 rounded-md text-blue-500 hover:bg-gray-100"
      >
        Login
      </button>
      <p class="text-sm text-blue-400 hover:text-blue-500 mt-2 mb-4">
        <a href="#">Lupa password?</a>
      </p>
      <p>
        Ingin mencoba? masuk
        <a href="#" class="text-blue-500">akun demo dulu</a>
      </p>

      <!-- DOWNLOAD FROM APP/PLAY STORE -->
      <hr class="my-4" />
      <div class="flex justify-center">
        <img
          class="h-12 mr-2"
          src="../assets/app-store-badge.png"
          alt="Download on app store"
        />
        <img
          class="h-12"
          src="../assets/play-store-badge.png"
          alt="Dowload on play store"
        />
      </div>

      <!-- CREDIT -->
      <div class="h-16 relative">
        <p class="text-gray-500 text-sm text-center absolute bottom-0 w-full">
          All rights &amp; reserverd 2008 - 2020
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import Input from '../components/buttons/Input'

export default {
  components: {
    Input,
  },
  data() {
    return {
      inputEmail: {
        faIcon: 'fas fa-user text-gray-400',
        faIconOnFocus: 'text-blue-500',
        placeholder: 'Email',
        focus: 'outline-none ring-1 ring-blue-500',
      },
      inputPassword: {
        type: 'password',
        placeholder: 'Password',
        faIcon: 'fas fa-lock text-gray-400',
        faIconOnFocus: 'text-blue-500',
        focus: 'outline-none ring-1 ring-blue-500',
        faIconButton: 'far fa-eye text-gray-400',
        faIconButtonHover: 'text-blue-500',
      },
    }
  },
  methods: {
    loginPasswordReveal(e) {
      e.type = e.type === 'password' ? 'text' : 'password'
    },
    loginRememberToggle() {
      let e = document.querySelector('#loginRemember')
      e.classList.toggle('bg-blue-500')
    },
  },
  mounted() {
    const e = document.querySelector('#title')
    e.text += ' | LOGIN'
  },
  beforeUnmount() {
    const e = document.querySelector('#title')
    e.text = e.text.slice(0, e.text.length - 8)
  },
}
</script>
