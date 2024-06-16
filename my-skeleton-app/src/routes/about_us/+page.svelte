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
</script>


<div>
    <Background />
    <TabSystem on:tabSelect={event => handleTabSelect(event.detail)} />
    {#if selectedTab === 1}
        <Bedsmovers />
    {:else if selectedTab === 2}
        <Popai />
    {:else if selectedTab === 3}
        <Illmattep />
    {/if}
</div>