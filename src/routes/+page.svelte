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
    <div class="grid mdp:grid-cols-3 lg:grid-cols-2 gap-y-10 mdp:gap-y-0 mdp:gap-x-10 grow">
        <div class="flex flex-col justify-center mdp:col-span-2 lg:col-span-1 row-start-2 mdp:row-start-1">
            <DetailsContent indexActive="{detailsIndexActive}"/>
        </div>
        
        <div class="flex flex-col justify-center mdp:col-span-1 row-start-1 mdp:row-start-1">
            <DetailsMenu on:itemSelection={onItemSelection}/>
        </div>
    </div>
</section>

<style scoped>
    section {
        top: -3vw
    }
</style>
