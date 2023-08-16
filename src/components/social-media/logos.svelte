<script>
    import configSocialMedia from '$config/social-media.js'
	import LogoSignal from '$components/social-media/logo-signal.svelte'
	import LogoThreema from '$components/social-media/logo-threema.svelte'
	import LogoWhatsapp from '$components/social-media/logo-whatsapp.svelte'
	import LogoDiscord from '$components/social-media/logo-discord.svelte'
	import LogoTelegram from '$components/social-media/logo-telegram.svelte'
	import LogoMail from '$components/social-media/logo-mail.svelte'

    const logos = {
        'signal': LogoSignal,
        'threema': LogoThreema,
        'whatsapp': LogoWhatsapp,
        'discord': LogoDiscord,
        'telegram': LogoTelegram,
        'mail': LogoMail,
    }
</script>

<ul class="flex flex-row pt-2 md:pt-0">
    {#each configSocialMedia.logos as logo, index (logo.id)}
        <li class="w-8 md:w-5 h-8 md:h-5 flex flex-col justify-center" class:md:ml-3={index > 0} class:ml-5={index > 0}>
            <svelte:component this={logos[logo.id]} {logo}/>
        </li>
    {/each}
</ul>
