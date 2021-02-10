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
      <input
        class="hidden"
        type="checkbox"
        name="loginRemember"
        id="loginRemember"
      />
      <label
        class="my-2 cursor-pointer block"
        for="loginRemember"
        @click="loginRememberToggle"
        ><i id="loginRememberIcon" class="mr-1 far fa-square text-gray-400"></i
        >Ingat saya</label
      >
      <Button v-bind="buttonLogin" />
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
import Input from '../components/UI/Input'
import Button from '../components/UI/Button'

export default {
  components: {
    Input,
    Button,
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
        faIconButton: 'far fa-eye text-gray-400 hover:text-blue-500',
      },
      buttonLogin: {
        title: 'Login',
        classes:
          'w-full p-2 border border-blue-500 rounded-md text-blue-500 hover:text-white hover:bg-blue-500 focus:bg-blue-700',
      },
    }
  },
  methods: {
    loginPasswordReveal(e) {
      e.type = e.type === 'password' ? 'text' : 'password'
    },
    loginRememberToggle() {
      let e = document.querySelector('#loginRememberIcon')
      ;['fa-square', 'fa-check-square', 'text-blue-500'].forEach((c) =>
        e.classList.toggle(c),
      )
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
