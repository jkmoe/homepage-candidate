<script>
	import ItemBase from '$components/details/content/item-base.svelte'
    import src from '$assets/img/experience.jpg'

	export let isActive

    const alt = 'Work experience'
</script>

<ItemBase {isActive} {src} {alt} />
