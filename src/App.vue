<template>
  <div class="bg-black">
    <nav class="flex bg-black items-center justify-between">
      <div class="flex gap-56 relative">
        <img class="md:w-32 w-20 md:ml-20 ml-5 mt-10" src="../src/images/logo.png" alt="">
        <svg @click="toggleMenu" class="w-10 text-white mt-10 md:hidden" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
        <path stroke-linecap="round" stroke-linejoin="round" d="M3.75 6.75h16.5M3.75 12h16.5M12 17.25h8.25"></path>
        </svg>
      </div>
      <div class="hidden md:block">
        <router-link class="mt-10 mr-10 text-white" to="/">Home</router-link> |
        <router-link class="mt-10 mr-10 text-white" to="/about">About</router-link>
        <router-link class="mt-10 mr-10 text-white" to="/service">Services</router-link>
        <router-link class="mt-10 mr-10 text-white" to="/portfolio">Portfolio</router-link>
        <router-link class="mt-10 mr-10 text-white" to="/contact">contact us</router-link>
        <router-link class=" text-end text-blue justify-center mr-20 mt-10 text-white bg-[#062E38] p-2 rounded-full" to="/started">Get Started</router-link>
      </div>
      
    </nav>
    <div class="flex flex-col bg-[#062E38] md:hidden absolute pb-5" v-if="showMenu">
      <router-link class="mt-10 text-white" to="/">Home</router-link> |
      <router-link class="mt-10 text-white" to="/about">About</router-link>
      <router-link class="mt-10 text-white" to="/service">Services</router-link>
      <router-link class="mt-10 text-white" to="/portfolio">Portfolio</router-link>
      <router-link class="mt-10 text-white" to="/contact">contact us</router-link>
      <router-link class=" text-end text-blue justify-center ml-20 mr-20 mt-10 text-[#062E38] bg-white p-2 rounded-full" to="/started">Get Started</router-link>
    </div>
  </div>
  <router-view/>
</template>

<script setup>
import { ref } from 'vue';
  const showMenu = ref(false)
  const toggleMenu = () => {
    showMenu.value = !showMenu.value
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  /* padding: 10px; */
  text-align: center;
  /* text-decoration: underline; */
  /* margin-top: 5px; */
  gap: 10px;
  
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}


</style>
