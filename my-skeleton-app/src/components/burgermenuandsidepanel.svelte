<script>
    import '../app.postcss';
    import { onMount } from 'svelte';


    let showPanel = false;

    function togglePanel() {
        showPanel = !showPanel;
        console.log(showPanel);
    }
</script>


<button on:click={togglePanel} class="btn btn-md variant-ghost-primary burger">
    <span class="burger-icon" class:active={showPanel}></span>
</button>

{#if showPanel}
    <div class="active fixed top-0 right-0 bg-dark-blurred h-dvh shadow-xl p-6 sm:w-full lg:w-1/5">
        <strong class="text-xl uppercase">bedsmovers</strong>
        <!-- close button -->
        <button on:click={togglePanel} class="btn btn-sm variant-ringed-tertiary top-0 right-0 fixed m-6"><strong>X</strong></button>
        <!-- content divider line-->
        <div class="border-t-2 border-surface-white opacity-35 mt-5 pb-5"></div>
        <!-- content -->
        <h1>Side Panel Content</h1>
        <p>This is the content of the side panel.</p>
    </div>
{/if}

<style>
    .burger {
        z-index: 9999;
    }
    
    
    .burger-icon {
        display: block;
        width: 30px;
        height: 3px;
        background-color: white;
        margin: 6px 0;
        transition: 0.4s;
    }
    .active {
        transform: translateX(0);
        z-index: 9999;
    }

</style>