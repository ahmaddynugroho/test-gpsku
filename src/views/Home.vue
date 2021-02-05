<template>
  <div class="home text-center my-8">
    <router-link :to="{ name: 'Login' }" class="hover:text-blue-500"
      >Login</router-link
    >
    |
    <router-link :to="{ name: 'Map' }" class="hover:text-blue-500"
      >Map</router-link
    >
  </div>
</template>

<script>
export default {
  name: 'Home',
}
</script>
