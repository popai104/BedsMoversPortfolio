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
<AppShell>
	<svelte:fragment slot="header">
		<Header />
	</svelte:fragment>	
	<slot />
	<svelte:fragment slot="footer">
		<Footer />
	</svelte:fragment>
</AppShell>
