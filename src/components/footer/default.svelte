<script>
    import SocialMediaLogos from '$components/social-media/logos.svelte'
</script>

<footer class="footer footer--default relative z-20 bg-gray-800 text-white">
    <div class="footer__content content-width py-2 flex flex-col-reverse md:flex-row justify-between">
        <div>Copyright &#169; 2023</div>
        <div class="social mb-2 md:mb-0">
            <SocialMediaLogos/>
        </div>
    </div>
</footer>

<style scoped>
    .footer--default {
        clip-path: inset(100% 0% 0% 0%);
        transition: clip-path var(--header-animation-duration) ease-in;
        transition-delay: var(--header-animation-delay);
    }

    :global(#app.mounted .footer--default) {
        clip-path: inset(0% 0% 0% 0%);
    }
</style>
