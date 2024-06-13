<script>
    import '../app.postcss';
    import { fade } from 'svelte/transition';
    import Footer from '../components/footercomponent.svelte'

    let showPanel = false;

    function togglePanel() {
        showPanel = !showPanel;
        console.log(showPanel);
    }

</script>



<button on:click={togglePanel} class="btn btn-md variant-ghost-primary burger" in:fade={{duration:400}} out:fade={{duration:400}}>
    <div class="flex flex-col">
        <span class="burger-icon"></span>
        <span class="burger-icon"></span>
        <span class="burger-icon"></span>
    </div>
</button>


{#if showPanel}
    <div class="sidepanel active fixed top-0 right-0 bg-surface-800 h-dvh shadow-xl p-6 w-full md:w-2/5 xl:w-1/5" in:fade={{duration:200}} out:fade={{duration:200}}>
        <strong class="text-xl uppercase">bedsmovers</strong>
        <!-- close button -->
        <button on:click={togglePanel} class="btn btn-sm variant-ringed-tertiary top-0 right-0 fixed m-6"><strong>X</strong></button>
        <!-- content divider line-->
        <div class="border-t-2 border-surface-white opacity-35 mt-5 pb-5"></div>
        <!-- content -->
        <div class="flex flex-col">
            <div class="flex flex-col space-y-2">
                <button class="btn btn-sm variant-soft-tertiary">Home</button>
                <button class="btn btn-sm variant-soft-tertiary">About us</button>
                <button class="btn btn-sm variant-soft-tertiary">Projects</button>
                <button class="btn btn-sm variant-soft-tertiary">Contacts</button>
                <button class="btn btn-sm variant-soft-tertiary">Move 'em beds!</button>
            </div>
        </div>
        <!-- bottom section -->
        <div class="bottom-section">
            <div class="border-t-2 border-surface-white opacity-35 mt-5 mx-6"></div>
            <div class="mx-6 -mt-6"><Footer /></div>
        </div>
    </div>
{/if}

<style>
    .burger {
        z-index: 9999;
    }
    
    
    .burger-icon {
        width: 15px;
        height: 1px;
        background-color: white;
        margin: 2px 0;
    }
    .active {
        transform: translateX(0);
        z-index: 9999;
    }

    .sidepanel {
        z-index: 9999;
    }

    .sidepanel .bottom-section {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
    }
</style>