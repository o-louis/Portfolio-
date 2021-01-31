<template>
	<nav
		class="w-10/12 h-10 flex justify-between items-center fixed top-0 py-6 z-50"
	>
		<span class="w-3/12 mr-3" />
		<ul class="flex flex-1 justify-between">
			<li
				v-for="(section, index) in menu"
				:key="index"
				class="text-white uppercase font-normal"
			>
				<a :href="section.href">{{ section.title }}</a>
			</li>
		</ul>
	</nav>
</template>

<script>
export default {
	name: 'Header',
	data() {
		return {
			menu: [
				{ title: 'Home', href: '#home' },
				{ title: 'About', href: '#about' },
				{ title: 'Projects', href: '#projects' },
			],
		}
	},
}
</script>

<style scoped>
nav {
	background: #101014;
}

span {
	height: 1px;
	background: rgba(255, 255, 255, 0.15);
}

@media (max-width: 320px) {
	span {
		display: none;
	}
}
</style>
