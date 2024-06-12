<script>
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


<button on:click={togglePanel}>
    <!-- Add your burger menu icon here -->
    <span>☰</span>
</button>

{#if showPanel}
    <div class="active fixed top-0 right-0 w-px:300 bg-surface-700 h-dvh shadow-xl p-6">
        <!-- Add your content for the side panel here -->
        <h1>Side Panel Content</h1>
        <p>This is the content of the side panel.</p>
    </div>
{/if}

<style>
    .side-panel {
        position: fixed;
        top: 0;
        left: 0;
        width: 300px;
        height: 100vh;
        background-color: #fff;
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
        transform: translateX(-100%);
        transition: transform 0.3s ease-in-out;
    }

    .active {
        transform: translateX(0);
        z-index: 9990;
    }
</style>