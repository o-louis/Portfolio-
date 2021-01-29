<template>
  <nav class="w-full flex justify-between items-center">
    <span class="w-3/12 mr-3" />
    <ul class="flex flex-1 justify-between">
      <li
        v-for="(section, index) in menu"
        :key="index"
        class="text-white uppercase font-normal"
      >
        {{ section.title }}
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      menu: [{ title: 'Home' }, { title: 'About' }, { title: 'Projects' }],
    }
  },
}
</script>

<style scoped>
span {
  height: 1px;
  background: rgba(255, 255, 255, 0.15);
}
</style>
