<script>
	import { createEventDispatcher } from 'svelte'
	import DetailsItem from '$components/details/menu/item.svelte'
	import configDetails from '$config/details.js'

	const dispatch = createEventDispatcher()

	let indexActive = 0

	function onItemSelection(index) {
		indexActive = index
		dispatch('itemSelection', {'itemIndex': index})
	}
</script>

<ul class="details-menu grid grid-cols-1 gap-y-3 text-white">
	{#each configDetails.content as contentItem, index (contentItem.id)}
		<DetailsItem
			title={contentItem.label}
			on:click={() => onItemSelection(index)}
			on:keypress={() => onItemSelection(index)}
			isActive={indexActive === index}
		/>
	{/each}
</ul>

<style scoped>
	:global(.details-menu li:nth-of-type(1)) {
		margin-left: 120px;
	}
	:global(.details-menu li:nth-of-type(2)) {
		margin-left: 45px;
	}
	:global(.details-menu li:nth-of-type(3)) {
		margin-left: 100px;
	}
</style>
