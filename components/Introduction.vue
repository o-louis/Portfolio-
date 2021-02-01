<template>
	<section
		id="home"
		class="text-white pt-28 sm:min-h-0 h-auto sm:pt-32 text-lg sm:text-xl md:w-10/12 lg:w-8/12"
	>
		<p class="opacity-0 text-xl sm:text-2xl md:text-3xl l1">Hello, I'm</p>
		<transition name="fade">
			<h1
				class="text-3xl font-bold ml-4 my-1 opacity-0 sm:text-4xl md:text-5xl transform translate-x-8 l2"
			>
				ORIANE LOUIS,
			</h1>
		</transition>
		<h2
			class="text-2xl font-semibold opacity-0 ml-12 transform translate-x-10 l3 sm:text-3xl md:text-4xl"
		>
			Front End Developer.
		</h2>

		<p class="mt-12 font-light leading-relaxed l4 opacity-0">
			I’m a <span class="font-medium">passionate developer</span> based in
			Montreal. I’m enthusiast about new technologies and I
			<span class="font-medium">love building things</span> and
			<span class="font-medium">improve user experience</span>.
		</p>

		<div class="flex justify-center mt-12 l5 opacity-0">
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

		<div class="chevron w-full mt-10 l5 opacity-0">
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
	mounted() {
		setInterval(() => {
			document.querySelector('.l1').classList.add('fade')
			stopTimer()
		}, 80)

		const stopTimer = () => {
			document.querySelector('.l2').classList.add('rightToLeft')
			document.querySelector('.l3').classList.add('rightToLeft')
			document.querySelector('.l4').classList.add('rightToLeft')
			document.querySelectorAll('.l5')[0].classList.add('rightToLeft')
			document.querySelectorAll('.l5')[1].classList.add('rightToLeft')
			clearInterval(timer)
			timer = null
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

.l1 {
	transition: opacity 0.25s ease;
}

.l2,
.l3,
.l4,
.l5 {
	transition: all 0.25s ease;
}

.l1.fade {
	transition-delay: 0.25s;
	opacity: 0.6;
}

.l2.rightToLeft {
	opacity: 1;
	transition-delay: 0.5s;
	transform: translateX(0px);
}

.l3.rightToLeft {
	opacity: 0.6;
	transition-delay: 0.75s;
	transform: translateX(0px);
}

.l4.rightToLeft {
	opacity: 0.6;
	transition-delay: 1s;
}
.l5.rightToLeft {
	opacity: 1;
	transition-delay: 1.25s;
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
