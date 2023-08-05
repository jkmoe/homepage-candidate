<script>
	import ItemBase from '$components/details/content/item-base.svelte'
	import Slider from '$components/slider/slider.svelte'
	import Mtg from '$components/details/content/projects/mtg.svelte'
	import Employ from '$components/details/content/projects/employ.svelte'
	import Ghi from '$components/details/content/projects/ghi.svelte'
	import Homepage from '$components/details/content/projects/homepage.svelte'
	import src from '$assets/img/projects.jpg'

	export let isActive

	const alt = 'Projects'
	let slider
	let currentSlide = 0
	const components = [Homepage, Ghi, Employ, Mtg]

	function previousSlide() {
		currentSlide = Math.max(0, currentSlide - 1)

		slider.moveTo(currentSlide)
	}

	function nextSlide() {
		currentSlide = Math.min(components.length - 1, currentSlide + 1)

		slider.moveTo(currentSlide)
	}
</script>

<ItemBase {isActive} {src} {alt}>
	<article class="relative">
		<div class="flex flex-row justify-between bg-white/90 p-2 mb-5 border">
			<h2>Projects</h2>
			<nav>
				<span
					class="font-medium"
					class:cursor-pointer={currentSlide !== 0}
					class:pointer-events-none={currentSlide === 0}
					class:opacity-20={currentSlide === 0}
					on:click={previousSlide}
				>Prev</span>
				<span class="text-emerald-600"> | </span>
				<span
					class="font-medium"
					class:cursor-pointer={currentSlide !== components.length - 1}
					class:pointer-events-none={currentSlide === components.length - 1}
					class:opacity-20={currentSlide === components.length - 1}
					on:click={nextSlide}
				>Next</span>
			</nav>
		</div>
		<Slider {components} {currentSlide} bind:this={slider}/>
	</article>
</ItemBase>
