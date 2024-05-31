<script>
    import '../app.postcss';
	import { AppBar } from '@skeletonlabs/skeleton';
</script>

<main>
    <AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
        <svelte:fragment slot="lead">
            <strong class="text-xl uppercase">bedsmovers</strong>
        </svelte:fragment>
        <svelte:fragment slot="default">
        </svelte:fragment>
        <svelte:fragment slot="trail">
        </svelte:fragment>
    </AppBar>
</main>

<style>
</style>