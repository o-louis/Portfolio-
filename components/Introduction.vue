<template>
	<section
		id="home"
		class="text-white pt-28 sm:min-h-0 h-auto sm:pt-32 text-lg sm:text-xl md:w-10/12 lg:w-8/12"
	>
		<p class="opacity-60 text-xl sm:text-2xl md:text-3xl">Hello, I'm</p>
		<h1 class="text-3xl font-bold ml-4 my-1 sm:text-4xl md:text-5xl">
			ORIANE LOUIS,
		</h1>
		<h2
			class="text-2xl font-semibold opacity-60 ml-12 sm:text-3xl md:text-4xl"
		>
			Front End Developer.
		</h2>

		<p class="mt-12 font-light opacity-60 leading-relaxed">
			I’m a <span class="font-medium">passionate developer</span> based in
			Montreal. I’m enthusiast about new technologies and I
			<span class="font-medium">love building things</span> and
			<span class="font-medium">improve user experience</span>.
		</p>

		<div class="flex justify-center mt-12">
			<a
				v-for="(social, index) in socialNetwork"
				:key="index"
				:href="social.link"
				target="_blank"
				><img
					:src="social.icon"
					:class="[
						socialNetwork.length - 1 != index ? 'pr-3' : '',
						'h-10 sm:h-10',
					]"
			/></a>
		</div>

		<div class="chevron w-full mt-10">
			<img :src="chevronDown" class="m-auto" />
		</div>
	</section>
</template>

<script>
export default {
	name: 'Introduction',
	data() {
		return {
			socialNetwork: [
				{
					icon: require('../assets/linkedin.svg'),
					link: 'https://www.linkedin.com/in/oriane-louis/',
				},
				{
					icon: require('../assets/github.svg'),
					link: 'https://github.com/o-louis',
				},
				{
					icon: require('../assets/codepen.svg'),
					link: 'https://codepen.io/reavenclaw',
				},
				{
					icon: require('../assets/mail.svg'),
					link: 'mailto:oriane.louis.pro@gmail.com',
				},
			],
			chevronDown: require('../assets/chevron-down.svg'),
		}
	},
}
</script>

<style scoped>
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

@media (max-width: 320px) {
	.chevron {
		display: none;
	}

	h2 {
		font-size: 20px;
	}
}
</style>
