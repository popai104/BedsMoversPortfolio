<script lang="ts">
    import '../app.postcss';
    import { AppBar, ListBox, ListBoxItem } from '@skeletonlabs/skeleton';
    import { popup } from '@skeletonlabs/skeleton';
    import type { PopupSettings } from '@skeletonlabs/skeleton';
    import { onMount, onDestroy } from 'svelte';

    let comboboxValue: string;
    let isHeaderVisible = true;
    let headerElement: HTMLElement;

    const popupCombobox: PopupSettings = {
        event: 'click',
        target: 'popupCombobox',
        placement: 'bottom',
        closeQuery: '.listbox-item'
    };

    // Intersection Observer callback
    const observerCallback = (entries: IntersectionObserverEntry[]) => {
        entries.forEach(entry => {
            isHeaderVisible = entry.isIntersecting;
        });
    };

    let observer: IntersectionObserver;

    $: {
        if (headerElement) {
            observer = new IntersectionObserver(observerCallback, { threshold: [0] });
            observer.observe(headerElement);
        }
    }

    onDestroy(() => {
        if (observer && headerElement) {
            observer.unobserve(headerElement);
        }
    });
</script>

<main>
    <AppBar bind:this={headerElement} class="header backdrop-filter backdrop-blur bg-dark-blurred sticky top-0 w-full border-b border-white border-opacity-20" background="" gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
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

    {#if !isHeaderVisible}
        <div class="fixed-div">
            Header is out of view
        </div>
    {/if}
</main>

<style type="postcss">
    .header {
        z-index: 10;
    }
    .fixed-div {
        position: fixed;
        top: 0;
        right: 0;
        margin-top: 16px;
        margin-right: 16px;
        padding: 8px;
        background-color: #1e40af; /* Tailwind blue-500 */
        color: white;
        border-radius: 4px;
    }
</style>
