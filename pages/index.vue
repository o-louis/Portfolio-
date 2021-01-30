<template>
	<div class="w-10/12 m-auto relative h-screen">
		<Header />
		<Introduction />
		<About />
	</div>
</template>

<script>
import Header from '@/components/Header.vue'
import Introduction from '@/components/Introduction.vue'
import About from '@/components/About.vue'

export default {
	name: 'Home',
	components: {
		Header,
		Introduction,
		About,
	},
	data() {
		return {}
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

html {
	scroll-behavior: smooth;
}

body {
	background: var(--background);
}
</style>
