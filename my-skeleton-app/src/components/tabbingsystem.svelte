<script>
    import { createEventDispatcher } from 'svelte';
    import { tweened } from 'svelte/motion';
    import { cubicOut } from 'svelte/easing';
    import { onMount } from 'svelte';

    const dispatch = createEventDispatcher();
    let selectedTab = 1;
    let tabs = ['BedsMovers', 'popai', 'illmattep'];

    const selectedStyle = tweened(
        { background: 'rgba(0, 0, 0, 0)', borderRadius: '20px' },
        { duration: 400, easing: cubicOut }
    );

    function selectTab(index) {
        selectedTab = index;
        dispatch('tabSelect', index);  // Dispatch event with the selected tab index
    }

    onMount(() => {
        selectTab(1); // Set the default selected tab
    });
</script>

<style>
    .tabs-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 15px;
    }

    .row {
        display: flex;
        justify-content: center;
        margin-bottom: 10px;
    }

    .tab-button {
        padding-top: 3px;
        padding-bottom: 2px;
        padding-left: 5px;
        padding-right: 5px;
        border: 2px solid rgba(204, 204, 204, 0.3);
        background: rgba(0, 0, 0, 0.05);
        margin: 0 5px;
        cursor: pointer;
        border-radius: 20px;
        transition: background 0.3s ease;
    }

    .tab-button.selected1 {
        background: rgba(218, 59, 59, 0.6);
    }
    .tab-button.selected2 {
        background: rgba(132, 5, 170, 0.6);
    }
    .tab-button.selected3 {
        background: rgba(63, 192, 51, 0.6);
    }

    .tab-button:hover {
        filter: brightness(1.1);
    }

    .btt1 {
        background: rgba(218, 59, 59, 0.2);
    }

    .btt2 {
        background: rgba(132, 5, 170, 0.2);
    }

    .btt3 {
        background: rgba(12, 241, 12, 0.2);
    }
</style>

<div class="tabs-container">
    <div class="row">
        <button
            class="tab-button btt1 {selectedTab === 1 ? 'selected1' : ''}"
            on:click={() => selectTab(1)}
            style="{selectedTab === 1 ? $selectedStyle : ''}"
        >
            {tabs[0]}
        </button>
    </div>
    <div class="row">
        <button
            class="tab-button btt2 {selectedTab === 2 ? 'selected2' : ''}"
            on:click={() => selectTab(2)}
            style="{selectedTab === 2 ? $selectedStyle : ''}"
        >
            {tabs[1]}
        </button>
        <button
            class="tab-button btt3 {selectedTab === 3 ? 'selected3' : ''}"
            on:click={() => selectTab(3)}
            style="{selectedTab === 3 ? $selectedStyle : ''}"
        >
            {tabs[2]}
        </button>
    </div>
</div>
