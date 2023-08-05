<script>
    import DetailsMenu from '$components/details/menu/items.svelte'
    import DetailsContent from '$components/details/content/items.svelte'

    let detailsIndexActive = 0

    function onItemSelection(event) {
        const index = event.detail.itemIndex

        if (detailsIndexActive !== index) {
            detailsIndexActive = index
        }
    }
</script>

<section class="relative flex flex-col grow content-width">
    <div class="grid grid-cols-2 gap-x-10 grow content-width">
        <div class="flex flex-col justify-center">
            <DetailsContent indexActive="{detailsIndexActive}"/>
        </div>
        
        <div class="flex flex-col justify-center">
            <DetailsMenu on:itemSelection={onItemSelection}/>
        </div>
    </div>
</section>

<style scoped>
    section {
        top: -3vw
    }
</style>
