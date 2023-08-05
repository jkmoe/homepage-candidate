<script>
    export let components
    export let currentSlide

    let slider
    const slides = []

    export function moveTo(slideIndex) {
        const slideWidth = slider.getBoundingClientRect().width
        const slideDistance = slideIndex * slideWidth

        for (const slide of slides) {
            slide.setAttribute('style', `left: -${slideDistance}px;`)
        }
    }
</script>

<div class="slider w-full relative" bind:this={slider}>
    <div class="slider-inner flex flex-row overflow-hidden">
        {#each components as component, index (index)}
            <div class="slide w-full shrink-0 relative left-0" class:invisible={index !== currentSlide} bind:this={slides[index]}>
                <svelte:component this={component} />
            </div>
        {/each}
    </div>
</div>

<style scoped>
    .slide {
        transition: left .6s ease-in-out;
    }
</style>