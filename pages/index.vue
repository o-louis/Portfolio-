<template>
  <div class="w-10/12 m-auto py-6 relative h-screen">
    <Header />
    <section class="text-white mt-12">
      <p class="opacity-60 text-lg">Hello, I'm</p>
      <h1 class="text-4xl ml-4 font-bold">ORIANE LOUIS,</h1>
      <h2 class="text-2xl ml-12 font-medium opacity-60">
        Front-End Developer.
      </h2>

      <p class="mt-12 font-light opacity-60 text-lg">
        I’m a <span class="font-medium">passionate developer</span> based in
        Montreal. I’m enthusiast about new technologies and I
        <span class="font-medium">love building things</span> and
        <span class="font-medium">improve user experience</span>.
      </p>

      <div class="flex justify-center mt-12">
        <a v-for="(social, index) in socialNetwork" :key="index"
          ><img
            :src="social.icon"
            :class="[socialNetwork.length - 1 != index ? 'pr-3' : '', 'h-10']"
        /></a>
      </div>
    </section>
    <div class="absolute bottom-3 w-full">
      <img :src="chevronDown" class="m-auto" />
    </div>
  </div>
</template>

<script>
import Header from '../components/Header.vue'

export default {
  name: 'Home',
  components: {
    Header,
  },
  data() {
    return {
      socialNetwork: [
        { icon: require('../assets/linkedin.svg') },
        { icon: require('../assets/github.svg') },
        { icon: require('../assets/codepen.svg') },
        { icon: require('../assets/mail.svg') },
      ],
      chevronDown: require('../assets/chevron-down.svg'),
    }
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Heebo:wght@300;400;500;700&display=swap');

:root {
  --background: #101014;
}

* {
  font-family: 'Heebo', sans-serif;
}

body {
  background: var(--background);
}
</style>
