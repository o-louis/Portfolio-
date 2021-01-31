<template>
	<section
		id="about"
		class="text-white min-h-screen sm:min-h-0 h-auto pt-28 sm:pt-32 sm:w-10/12 lg:w-8/12"
	>
		<h2 class="uppercase text-xl mb-5 sm:text-2xl md:text-3xl">
			More about me
		</h2>
		<p
			class="font-light text-lg opacity-60 leading-relaxed sm:text-xl sm:leading-relaxed md:leading-relaxed"
		>
			I am skilled in
			<span class="font-medium"
				>JavaScript, React.js, Vue.js and Node.js</span
			>. I have worked on a variety of projects on
			<span class="font-medium">Web and Tvs</span> from design to
			development and I find myself capable enough to
			<span class="font-medium">handle pressure well</span>. I'm a bit
			perfectionist so I like projects well-organized.
			<span class="font-medium">Quick learner</span> describes me well.
		</p>

		<ul class="flex flex-wrap mt-8">
			<li
				v-for="(skill, index) in skills"
				:key="index"
				class="text-white mr-3 mt-3 py-1 px-4 md:text-lg"
			>
				{{ skill }}
			</li>
		</ul>
	</section>
</template>

<script>
export default {
	name: 'About',
	data() {
		return {
			skills: [
				'Javascript',
				'Typescript',
				'Vue.js',
				'React.js',
				'Node.js',
				'NextJS',
				'HTML',
				'CSS',
				'SASS',
				'Bootstrap',
				'jQuery',
				'TailwindCSS',
				'Webpack',
				'MongoDB',
				'Python',
				'Figma',
			],
		}
	},
}
</script>

<style scoped>
li {
	background: rgb(37, 37, 48);
	border-radius: 8px;
}
</style>
