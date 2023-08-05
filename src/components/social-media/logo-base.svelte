<script>
    export let logo
    export let src
    
    const alt = logo.alt
    const title = alt
    const href = logo.linkTarget
</script>

<a {href} {title}>
    <img {src} {alt}>
</a>
