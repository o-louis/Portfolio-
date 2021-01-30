<template>
  <div class="w-10/12 m-auto py-6 relative h-screen">
    <Header />
    <Introduction />
    <div class="chevron absolute bottom-10 w-full">
      <img :src="chevronDown" class="m-auto" />
    </div>
  </div>
</template>

<script>
import Header from '../components/Header.vue'
import Introduction from '@/components/Introduction.vue'

export default {
  name: 'Home',
  components: {
    Header,
    Introduction,
  },
  data() {
    return {
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

.chevron {
  animation-duration: 0.8s;
  animation-name: bounce;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}

@keyframes bounce {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(20px);
  }
}
</style>
