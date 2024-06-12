<script>
	import '../app.postcss';
	import { AppShell } from '@skeletonlabs/skeleton';
	import Header from '../components/headercomponent.svelte' ;
	import Footer from '../components/footercomponent.svelte' ;
	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
</script>

<!-- App Shell -->
<main>
    <Header />
    <slot />
    <Footer />
</main>

<style>
    :global(#app-shell) {
        display: flex;
        flex-direction: column;
        min-height: 100vh;
    }
        :global(#app-shell > *) {
        flex-shrink: 0;
    }
    :global(#main-content) {
        flex-grow: 1;
    }
</style>