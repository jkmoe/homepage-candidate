<script>
    export let title
    export let isActive

    $: ariaDisabled = isActive ? 'true' : 'false'
</script>

<li class="menu-item rounded-sm overflow-hidden">
    <div on:click on:keypress
        class="menu-item__inner flex align-middle justify-end pr-3 h-10 bg-gray-800 relative hover:gradient"
        class:menu-item__inner--active={isActive}
        class:cursor-default={isActive}
        role="button"
        tabindex="0"
        aria-disabled={ariaDisabled}
    >
        <span class="menu-item__text text-2xl tracking-wider font-medium px-2 select-none">{ title }</span>
    </div>
</li>

<style lang="postcss" scoped>
    .menu-item__inner::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        @apply gradient;
        width: 100%;
        height: 0;
        transition: height .3s linear;
    }

    .menu-item__inner--active::after {
        height: .3em;
    }
</style>
