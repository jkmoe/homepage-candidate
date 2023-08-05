<header class="header header--default relative">
	<div class="header__content h-14"/>
	<div class="header__tail h-[--header-tail-height] max-h-[--header-tail-max-height] bg-[--document-background-color]"/>
</header>

<style lang="postcss" scoped>
    .header--default {
        @apply gradient;
        clip-path: inset(0% 0% -1% 100%);
        transition: clip-path var(--header-animation-duration) ease-in;
        transition-delay: var(--header-animation-delay);
    }

    :global(#app.mounted .header--default) {
        clip-path: inset(0% 0% -1% 0%);
    }

    .header__tail {
        clip-path: ellipse(110% 100% at 100% 100%);
    }
</style>
