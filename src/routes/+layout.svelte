<script lang="ts">
	import '../app.postcss';

    import iconImg from "$lib/assets/Icon.png";
    import {page} from '$app/stores';
    import PageFooter from "$lib/components/PageFooter.svelte";

    let icon = iconImg !== undefined ? iconImg : "./favicon.ico";

    export let data;

    // Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
    import {AppBar, AppShell, storePopup} from '@skeletonlabs/skeleton';
    import PageTransition from "$lib/components/PageTransition.svelte";
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>


<AppShell>
    <svelte:fragment slot="header">
        <AppBar>
            <svelte:fragment slot="lead"><a href="/" class="inline-flex">
                <img alt="Uleth Icon" src={icon} class="w-1/6 h-1/6"/>
                <p class="ml-2 my-auto font-bold">Cole's Portfolio</p> </a>
            </svelte:fragment>
            <a href="/social-science/" class="{$page.url.pathname === '/social-science' ? 'underline' : ''}">Social Science</a>
            <a href="/humanities/" class="{$page.url.pathname === '/humanities' ? 'underline' : ''}">Humanities</a>
            <a href="/fine-arts/" class="{$page.url.pathname === '/fine-arts' ? 'underline' : ''}">Fine Arts</a>
        </AppBar>
    </svelte:fragment>
    <!-- Router Slot -->
    <PageTransition pathname={data.pathname}>
        <slot />
    </PageTransition>
    <!-- ---- / ---- -->
    <svelte:fragment slot="pageFooter"><PageFooter/></svelte:fragment>
    <!-- (footer) -->
</AppShell>
