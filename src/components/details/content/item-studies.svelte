<script>
	import ItemBase from '$components/details/content/item-base.svelte'
	import src from '$assets/img/university-of-applied-sciences.jpg'

	export let isActive

	const alt = 'University of Applied Sciences Flensburg'
</script>

<ItemBase {isActive} {src} {alt}>
	<article class="relative">
		<h2 class="bg-white/90 p-2 mb-5 border">Studies</h2>
		
		<div class="content-grid">
			<div class="italic">Programme Title</div>
			<div>Applied Computer Science</div>

			<div class="italic">Degree</div>
			<div>Bachelor of Science</div>

			<div class="italic">Location</div>
			<div>Flensburg, Germany</div>

			<div class="italic">CP Progress</div>
			<div>{Math.floor(55/210*100)}% (55/210)</div>

			<div class="italic">Year of Graduation</div>
			<div>2026</div>
		</div>
	</article>
</ItemBase>

<style scoped>
</style>
