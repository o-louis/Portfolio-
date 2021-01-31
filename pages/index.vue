<template>
	<div class="wrapper w-10/12 m-auto relative">
		<Header />
		<Introduction />
		<About />
		<Projects />
		<footer class="text-white text-center">
			<p>Made with ❤️ by Oriane Louis</p>
			<p>© 2020, Built with NuxtJS</p>
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
	mounted() {
		let _this = this
		window.addEventListener(
			'scroll',
			function () {
				const sections = document.querySelectorAll('section')
				_this.sectionsTop = Array.from(sections).map(
					(section) => section.offsetTop
				)
				_this.paused = false
				if (
					document.body.getBoundingClientRect().top > _this.scrollPos
				) {
					if (!_this.paused) {
						console.log('up')
						if (_this.counter - 1 > -1) _this.counter--
						_this.paused = true
					}
				} else {
					if (!_this.paused) {
						console.log('down')
						if (_this.counter + 1 < _this.sectionsTop.length)
							_this.counter++
						_this.paused = true
					}
				}
				_this.scrollPos = document.body.getBoundingClientRect().top
				// document.documentElement.scrollTop = this.sectionsTop[this.counter]
			},
			false
		)
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
