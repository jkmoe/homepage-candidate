<script>
    export let isActive
    export let src
    export let alt
</script>

<div class="content-item absolute top-0 left-0 w-full" class:content-item--active={isActive}>
    <div class="item-details relative">
		<div class="item-details__img-wrapper absolute top-0 left-0 rounded-sm overflow-hidden">
			<img class="item-details__img" {src} {alt} width="200" height="200" />
		</div>

        <div class:invisible={!isActive}>
            <slot/>
        </div>
	</div>
    
</div>

<style lang="postcss" scoped>
    .content-item {
        clip-path: inset(0% 0% 0% 100%);
        transition: clip-path .7s ease-in;
    }

    .content-item--active {
        clip-path: inset(0% 0% 0% 0%);
    }

    .item-details {
		min-width: 300px;
		min-height: 300px;
        padding-top: 80px;
        padding-left: 140px;
	}

	.item-details__img-wrapper {
		width: 200px;
		height: 200px;
	}

    .item-details__img {
        opacity: .85;
        filter: grayscale(80%);
    }
</style>
