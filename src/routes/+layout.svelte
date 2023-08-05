<script>
	import { onMount } from 'svelte'
	import '$assets/css/app.css'
	import '$assets/css/font.css'
	import Header from '$components/header/default.svelte'
	import Footer from '$components/footer/default.svelte'

	onMount(() => {
		const elApp = document.querySelector('#app')
		elApp.classList.add('mounted')
	})
</script>

<Header/>

<main class="grow relative flex flex-col opacity-0 -right-40">
	<slot/>
</main>

<Footer/>

<style scoped>
	main {
		transition: right var(--main-animation-duration) ease-out, opacity var(--main-animation-duration) ease-out;
		transition-delay: var(--main-animation-delay);
	}

	:global(#app.mounted main) {
        right: 0;
		opacity: 1;
    }
</style>