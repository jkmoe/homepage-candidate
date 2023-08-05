<script>
	import { onMount } from 'svelte'
	import configDetails from '$config/details.js'
	import ItemStudies from '$components/details/content/item-studies.svelte'
	import ItemProjects from '$components/details/content/item-projects.svelte'
	import ItemJob from '$components/details/content/item-job.svelte'
	import ItemExperience from '$components/details/content/item-experience.svelte'

	export let indexActive

	const components = [ItemStudies, ItemProjects, ItemJob, ItemExperience]
	let itemElements = []
	let itemsWrapperElement

	onMount(() => {
		itemElements = document.querySelectorAll('.content-items .content-item')

		setHeight()

		window.addEventListener('resize', setHeight)

		return () => {
			window.removeEventListener('resize', setHeight)
		}
	})

	function setHeight() {
		let maxHeight = 0

		for (const element of itemElements) {
			maxHeight = Math.max(element.getBoundingClientRect().height, maxHeight)
		}

		itemsWrapperElement.setAttribute('style', `height: ${maxHeight}px;`)
	}
</script>

<div class="content-items relative" bind:this={itemsWrapperElement}>
	{#each configDetails.content as contentItem, index (contentItem.id)}
		<svelte:component this={components[index]} isActive={index === indexActive} />
	{/each}
</div>
