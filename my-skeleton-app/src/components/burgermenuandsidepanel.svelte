<script>
    import '../app.postcss';
    import { onMount } from 'svelte';


    let showPanel = false;

    function togglePanel() {
        showPanel = !showPanel;
        console.log(showPanel);
    }

    onMount(() => {
        // Add any additional logic you need when the component is mounted
    });
</script>


<button on:click={togglePanel} class="btn btn-xl">
    <!-- Add your burger menu icon here -->☰
</button>

{#if showPanel}
    <div class="active fixed top-0 right-0 w-px:300 bg-surface-700 h-dvh shadow-xl p-6">
        <!-- Add your content for the side panel here -->
        <h1>Side Panel Content</h1>
        <p>This is the content of the side panel.</p>
    </div>
{/if}

<style>
    .active {
        transform: translateX(0);
        z-index: 9990;
    }
</style>