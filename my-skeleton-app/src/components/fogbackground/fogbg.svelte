<script>
    import { onMount, onDestroy, afterUpdate } from 'svelte';

    export let highlightColor = 0x0;
    export let midtoneColor = 0xb400ff;
    export let lowlightColor = 0x0;
    export let baseColor = 0x0;

    let fogEffect;
    let vantaContainer;

    onMount(() => {
        // Load Three.js and Vanta.js
        const loadScripts = async () => {
            const threeScript = document.createElement('script');
            threeScript.src = 'https://cdnjs.cloudflare.com/ajax/libs/three.js/r134/three.min.js';
            document.head.appendChild(threeScript);

            threeScript.onload = () => {
                const vantaScript = document.createElement('script');
                vantaScript.src = 'https://cdnjs.cloudflare.com/ajax/libs/vanta/0.5.21/vanta.fog.min.js';
                document.head.appendChild(vantaScript);

                vantaScript.onload = () => {
                    fogEffect = VANTA.FOG({
                        el: vantaContainer,
                        mouseControls: true,
                        touchControls: true,
                        gyroControls: false,
                        minHeight: 200.00,
                        minWidth: 200.00,
                        highlightColor,
                        midtoneColor,
                        lowlightColor,
                        baseColor,
                        blurFactor: 0.65,
                        speed: 1.00,
                        zoom: 1.20
                    });
                };
            };
        };

        loadScripts();
    });

    afterUpdate(() => {
        if (fogEffect) {
            fogEffect.setOptions({
                highlightColor,
                midtoneColor,
                lowlightColor,
                baseColor
            });
        }
    });

    onDestroy(() => {
        if (fogEffect) fogEffect.destroy();
    });
</script>

<style>
    #vanta-fog {
        width: 100%;
        height: 100vh; /* Adjust this as needed */
        position: absolute;
        top: 0;
        left: 0;
        z-index: -1; /* Ensure it is behind other content */
    }
</style>

<div id="vanta-fog" bind:this={vantaContainer}></div>
