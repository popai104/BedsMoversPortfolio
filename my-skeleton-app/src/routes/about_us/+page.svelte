<script>
    import TabSystem from "../../components/tabbingsystem.svelte";
    import Bedsmovers from "../about_us/tabs/bedsmovers.svelte";
    import Popai from "../about_us/tabs/popai.svelte";
    import Illmattep from "../about_us/tabs/illmattep.svelte";
    import Background from "../../components/fogbackground/fogbg.svelte";
    
    let selectedTab = 1;
    
    function handleTabSelect(tabIndex) {
        selectedTab = tabIndex;
    }
    
    // Define colors for each tab
    const tabColors = [
    { highlightColor: 0x000000, midtoneColor: 0x840000, lowlightColor: 0x000000, baseColor: 0x0 },
    { highlightColor: 0x000000, midtoneColor: 0xaf06cf, lowlightColor: 0x000000, baseColor: 0x0 },
    { highlightColor: 0x000000, midtoneColor: 0x398533, lowlightColor: 0x000000, baseColor: 0x0 }
    ];
</script>


<div>
    <Background
    bind:highlightColor={tabColors[selectedTab - 1].highlightColor}
    bind:midtoneColor={tabColors[selectedTab - 1].midtoneColor}
    bind:lowlightColor={tabColors[selectedTab - 1].lowlightColor}
    bind:baseColor={tabColors[selectedTab - 1].baseColor}
    />
    <TabSystem on:tabSelect={event => handleTabSelect(event.detail)} />
    {#if selectedTab === 1}
    <Bedsmovers />
    {:else if selectedTab === 2}
    <Popai />
    {:else if selectedTab === 3}
    <Illmattep />
    {/if}
</div>