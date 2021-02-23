<template>
	<section
		id="projects"
		class="text-white sm:min-h-0 h-auto pt-28 sm:pt-32 sm:w-10/12"
		v-scroll-reveal.reset
	>
		<h2 class="uppercase text-xl mb-6 sm:text-2xl md:text-3xl lg:text-4xl">
			My Projects
		</h2>
		<div class="grid sm:grid-cols-1 lg:grid-cols-3 gap-5">
			<div
				v-for="(project, index) in projects"
				:key="index"
				class="project-img relative overflow-hidden max-w-xl sm:w-96 sm:h-52 md:w-10/12 md:max-w-md lg:h-52 lg:max-w-xl lg:w-full"
			>
				<img :src="project.img" class="object-cover h-full w-full" />
				<div
					class="project-info absolute top-0 w-full h-full text-sm px-6 flex flex-col justify-center flex flex-col sm:text-base md:px-10"
				>
					<p class="text-lg sm:text-xl">
						{{ project.title }}
					</p>
					<p class="italic">{{ project.resume }}</p>
					<div class="flex justify-between mt-8">
						<button
							class="border p-1 rounded w-16 hover:bg-white hover:text-black sm:w-20"
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
import urlShortener from '@/assets/url-shortener.png'
import spotifyClone from '@/assets/spotify-clone.png'
import reachatt from '@/assets/reachatt.png'

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
				{
					img: urlShortener,
					title: 'Url Shortener',
					resume: 'Short urls only in local',
					url: 'https://srrt.netlify.app/',
					source: 'https://github.com/o-louis/url-shortener',
				},
				{
					img: spotifyClone,
					title: 'Spotify Clone Integration',
					resume: 'Not efficient just visual',
					url: 'https://spotify-clone01.netlify.app/',
					source: 'https://github.com/o-louis/spotify-clone',
				},
				{
					img: reachatt,
					title: 'Live chat',
					resume: 'Made with react, you can create or join a room',
					url: 'https://reachatt.netlify.app/',
					source: 'https://github.com/o-louis/react-chat-app',
				}
			],
		}
	},
}
</script>

<style scoped>
.project-info {
	background: black;
	transform: translateY(-100%);
	transition: transform 0.4s ease-in-out;
}
.project-img:hover .project-info {
	transform: translateY(0);
}

/* img {
	filter: gray;
	-webkit-filter: grayscale(1);
	filter: grayscale(1);
} */
</style>
