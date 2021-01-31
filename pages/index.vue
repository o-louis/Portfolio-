<template>
	<div class="wrapper w-10/12 m-auto relative">
		<Header />
		<Introduction />
		<About />
		<Projects />
		<footer class="text-white text-center mb-4">
			<p>Made with ❤️ by Oriane Louis</p>
			<p>© 2021, Built with NuxtJS</p>
		</footer>
	</div>
</template>

<script>
import Header from '@/components/Header.vue'
import Introduction from '@/components/Introduction.vue'
import About from '@/components/About.vue'
import Projects from '@/components/Projects.vue'

export default {
	name: 'Home',
	components: {
		Header,
		Introduction,
		About,
		Projects,
	},
	data() {
		return {
			sectionsTop: [],
			lastScrollPosition: 0,
			counter: 0,
			currentCounter: 1,
			currentSection: 0,
			scrollPos: 0,
			paused: false,
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

section {
	height: 88vh;
}
</style>
