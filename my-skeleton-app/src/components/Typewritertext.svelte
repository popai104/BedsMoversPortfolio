<script>
    import { onMount } from 'svelte';

    let textElement;
    const textContent = [
        "Hello, ",
        "welcome to the ",
        { word: "BedsMovers", color: "text-primary-500 font-bold" },
        " portfolio demo.",
        " have a ",
        { word: "fun", color: "text-primary-300 font-bold" },
        " look around!",
    ];

    let charIndex = 0;
    let wordIndex = 0;
    let isErasing = false;
    const typingSpeed = 40;
    const erasingSpeed = 20;
    const newTextDelay = 100;
    const erasingDelay = 30;

    function type() {
        if (wordIndex < textContent.length) {
            if (typeof textContent[wordIndex] === 'string') {
                if (!isErasing) {
                    textElement.innerHTML += textContent[wordIndex][charIndex];
                    charIndex++;
                    if (charIndex === textContent[wordIndex].length) {
                        charIndex = 0;
                        wordIndex++;
                        setTimeout(type, newTextDelay);
                    } else {
                        setTimeout(type, typingSpeed);
                    }
                } else {
                    textElement.innerHTML = textElement.innerHTML.substring(0, textElement.innerHTML.length - 1);
                    if (textElement.innerHTML.length === 0) {
                        isErasing = false;
                        wordIndex++;
                        setTimeout(type, typingSpeed);
                    } else {
                        setTimeout(type, erasingSpeed);
                    }
                }
            } else if (typeof textContent[wordIndex] === 'object') {
                if (!isErasing) {
                    textElement.innerHTML += `<span class="${textContent[wordIndex].color}">${textContent[wordIndex].word[charIndex]}</span>`;
                    charIndex++;
                    if (charIndex === textContent[wordIndex].word.length) {
                        charIndex = 0;
                        wordIndex++;
                        setTimeout(type, newTextDelay);
                    } else {
                        setTimeout(type, typingSpeed);
                    }
                } else {
                    textElement.innerHTML = textElement.innerHTML.substring(0, textElement.innerHTML.length - 1);
                    if (textElement.innerHTML.length === 0) {
                        isErasing = false;
                        wordIndex++;
                        setTimeout(type, typingSpeed);
                    } else {
                        setTimeout(type, erasingSpeed);
                    }
                }
            }
        } else if (!isErasing) {
            isErasing = true;
            setTimeout(type, erasingDelay);
        }
    }

    onMount(() => {
        setTimeout(type, newTextDelay);
    });
</script>


<div class="terminal">
    <div class="hidden word-red word-blue word-green"></div>
    <div>
        <span id="typewriter-text" bind:this={textElement}></span>
        <span id="cursor"></span>
    </div>
</div>

<style>
    #typewriter-text {
        display: inline-block;
        color: #fff;
        font-size:calc(2vw + 3vh);
        margin-top: 0;
        line-height: 1;
    }

    #cursor {
        display: inline-block;
        width: calc(2vw + 1vh);
        height: calc(2vw + 3vh);
        background-color: rgb(255, 255, 255);
        margin-left: 2px;
        animation: blink 0.5s step-end infinite;
    }

    @keyframes blink {
        50% {
            opacity: 0;
        }
    }

</style>