<script>
	import ItemBase from '$components/details/content/item-base.svelte'
	import src from '$assets/img/leapfrog-flensburg.jpg'

	export let isActive

	const alt = 'leapfrog GmbH'
</script>

<ItemBase {isActive} {src} {alt}>
	<article class="relative">
		<h2 class="bg-white/90 p-2 mb-5 border">Job</h2>

		<div class="content-grid">
			<div class="italic">Company</div>
			<div>
				<a href="https://leapfrog.com.de/en" target="_blank">leapfrog gmbh</a>
			</div>

			<div class="italic">Current Position</div>
			<div>Nuxt & Laravel Developer</div>

			<div class="italic">Weekly Working Hours</div>
			<div>20</div>

			<div class="italic">Year of Entrance</div>
			<div>2022</div>

			<div class="italic">Location</div>
			<div>Flensburg, Germany</div>
		</div>
	</article>
</ItemBase>

<style scoped>
</style>
