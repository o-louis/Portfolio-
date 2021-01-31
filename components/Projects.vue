<template>
	<section id="projects" class="text-white min-h-screen h-auto pt-28">
		<h2 class="uppercase text-xl mb-6">My Projects</h2>
		<div>
			<div
				v-for="(project, index) in projects"
				:key="index"
				class="project-img relative mb-4 overflow-hidden"
			>
				<img :src="project.img" />
				<div
					class="project-info absolute top-0 w-full h-full text-sm p-4 flex flex-col"
				>
					<p class="text-lg">{{ project.title }}</p>
					<p class="italic">{{ project.resume }}</p>
					<div class="flex justify-between mt-8">
						<button
							class="border p-1 rounded w-16 hover:bg-white hover:text-black"
						>
							<a :href="project.url" target="_blank">View</a>
						</button>
						<button class="hover:underline">
							<a :href="project.source" target="_blank">Source</a>
						</button>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<script>
import codetips from '@/assets/codetips.png'
import covidtracker from '@/assets/covidtracker.png'
import vueflix from '@/assets/vueflix.png'

export default {
	name: 'Projects',
	data() {
		return {
			projects: [
				{
					img: codetips,
					title: 'CodeTips',
					resume: 'Gather a list of Javascript Fundamentals',
					url: 'https://code-tips.netlify.app/',
					source: 'https://github.com/o-louis/CodeTips',
				},
				{
					img: covidtracker,
					title: 'Covid Tracker',
					resume: 'Follow the covid pandemic in real time',
					url: 'https://covid-trackerv2.netlify.app/',
					source: 'https://github.com/o-louis/covid-tracker-v2',
				},
				{
					img: vueflix,
					title: 'VueFlix',
					resume: 'Check out the popular and top rated movies',
					url: 'https://vueflixx.netlify.app/',
					source: 'https://github.com/o-louis/movie-vuejs',
				},
			],
		}
	},
}
</script>

<style scoped>
.project-info {
	background: rgb(37, 37, 48);
	transform: translateY(-100%);
	transition: transform 0.4s ease-in-out;
}
.project-img:hover .project-info {
	transform: translateY(0);
}
</style>
