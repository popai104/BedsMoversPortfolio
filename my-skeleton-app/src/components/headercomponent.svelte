<script lang="ts">
    import '../app.postcss';
	import { AppBar, ListBox, ListBoxItem } from '@skeletonlabs/skeleton';
    import { popup } from '@skeletonlabs/skeleton';
    import type { PopupSettings } from '@skeletonlabs/skeleton';

    let comboboxValue: string;

    const popupCombobox: PopupSettings = {
        event: 'click',
        target: 'popupCombobox',
        placement: 'bottom',
        closeQuery: '.listbox-item'
    };     
</script>


<main>
    <AppBar class="backdrop-filter backdrop-blur bg-dark-blurred fixed top-0 w-full border-b border-white border-opacity-20" background="" gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">  
        <svelte:fragment slot="lead">
            <strong class="text-xl uppercase">bedsmovers</strong>
        </svelte:fragment>
        <svelte:fragment slot="default">
            <div class="hidden md:flex space-x-2">
                <button class="btn btn-sm variant-ghost-primary">Home</button>
                <button class="btn btn-sm variant-ghost-primary">About us</button>
                <button class="btn btn-sm variant-ghost-primary">Projects</button>
                <button class="btn btn-sm variant-ghost-primary">Contacts</button>
                <button class="btn btn-sm variant-ghost-primary">Move 'em beds!</button>
            </div>
        </svelte:fragment>
        <svelte:fragment slot="trail">
            <!--TODO: burger menu :D-->


            <!--Language selection dropdown-->
            <div class="hidden md:flex">
                <button class="btn btn-sm variant-ghost-tertiary justify-between" use:popup={popupCombobox}>
                    <span class="capitalize">{comboboxValue ?? 'language'}</span>
                    <span>↓</span>
                </button>
                <div class="card shadow-xl py-2 rounded-xl" data-popup="popupCombobox">
                    <ListBox rounded="rounded-none">
                        <ListBoxItem bind:group={comboboxValue} name="placeholder" value="placeholder">Coming Soon...</ListBoxItem>
                    </ListBox>
                    <div class="arrow bg-surface-100-800-token" />
                </div>
            </div>                      
        </svelte:fragment>
    </AppBar>
</main>

<style type="postcss">

</style>