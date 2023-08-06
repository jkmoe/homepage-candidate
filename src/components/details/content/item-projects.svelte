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

	$: isFirstSlideActive = currentSlide === 0
	$: isLastSlideActive = currentSlide === components.length - 1

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
			<nav class="select-none">
				<span
					class="font-medium"
					class:cursor-pointer={!isFirstSlideActive}
					class:pointer-events-none={isFirstSlideActive}
					class:opacity-20={isFirstSlideActive}
					on:click={previousSlide}
					on:keypress={previousSlide}
					role="button"
					tabindex="0"
					aria-disabled={isFirstSlideActive}
				>Prev</span>
				<span class="text-emerald-600"> | </span>
				<span
					class="font-medium"
					class:cursor-pointer={!isLastSlideActive}
					class:pointer-events-none={isLastSlideActive}
					class:opacity-20={isLastSlideActive}
					on:click={nextSlide}
					on:keypress={nextSlide}
					role="button"
					tabindex="0"
					aria-disabled={isLastSlideActive}
				>Next</span>
			</nav>
		</div>
		<Slider {components} {currentSlide} bind:this={slider}/>
	</article>
</ItemBase>
