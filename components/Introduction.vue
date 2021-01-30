<template>
  <section class="text-white mt-12">
    <p class="opacity-60 text-lg">Hello, I'm</p>
    <h1 class="text-4xl ml-4 font-bold">ORIANE LOUIS,</h1>
    <h2 class="text-2xl ml-12 font-medium opacity-60">Front-End Developer.</h2>

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
</template>

<script>
export default {
  name: 'Introduction',
  data() {
    return {
      socialNetwork: [
        { icon: require('../assets/linkedin.svg') },
        { icon: require('../assets/github.svg') },
        { icon: require('../assets/codepen.svg') },
        { icon: require('../assets/mail.svg') },
      ],
    }
  },
}
</script>

<style lang="scss" scoped></style>
