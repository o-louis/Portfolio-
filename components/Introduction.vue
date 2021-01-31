<template>
	<section id="home" class="text-white pt-28 min-h-screen h-auto text-lg">
		<p class="opacity-60 text-xl">Hello, I'm</p>
		<h1 class="text-3xl font-bold ml-4 my-1">ORIANE LOUIS,</h1>
		<h2 class="text-2xl font-semibold opacity-60 ml-12">
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
						'h-10',
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
