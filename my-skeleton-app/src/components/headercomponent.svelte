<script lang="ts">
    import '../app.postcss';
    import { AppBar, ListBox, ListBoxItem } from '@skeletonlabs/skeleton';
    import { popup } from '@skeletonlabs/skeleton';
    import type { PopupSettings } from '@skeletonlabs/skeleton';
    import { onMount, onDestroy, afterUpdate } from 'svelte';
    import BurgerMenu from './burgermenuandsidepanel.svelte';

    let comboboxValue: string;
    let isHeaderVisible = true;
    let headerElement: HTMLElement | null = null;
    let headerContainer: HTMLDivElement | null = null;

    const popupCombobox: PopupSettings = {
        event: 'click',
        target: 'popupCombobox',
        placement: 'bottom',
        closeQuery: '.listbox-item'
    };

    const observerCallback = (entries: IntersectionObserverEntry[]) => {
        entries.forEach(entry => {
            isHeaderVisible = entry.isIntersecting;
        });
    };

    let observer: IntersectionObserver;

    onMount(() => {
        observer = new IntersectionObserver(observerCallback, { threshold: [0] });

        if (headerContainer) {
            observer.observe(headerContainer);
        }
    });

    afterUpdate(() => {
        if (headerContainer && !observer) {
            observer = new IntersectionObserver(observerCallback, { threshold: [0] });
            observer.observe(headerContainer);
        }
    });

    onDestroy(() => {
        if (observer && headerContainer) {
            observer.unobserve(headerContainer);
        }
    });
</script>

<main>
    <div bind:this={headerContainer} class="header-container">
        <AppBar class="header backdrop-filter backdrop-blur bg-dark-blurred sticky top-0 w-full border-b border-white border-opacity-20" background="" gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
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
                <div class="md:hidden"><BurgerMenu /></div>
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
    </div>

    {#if !isHeaderVisible}
        <div class="fixed-div">
            <BurgerMenu />
        </div>
    {/if}
</main>

<style type="postcss">
    .fixed-div {
        position: fixed;
        top: 0;
        right: 0;
        margin-top: 16px;
        margin-right: 16px;
    }
</style>
