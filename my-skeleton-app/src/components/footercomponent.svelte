<script>
    import { onMount } from 'svelte';
    import '../app.postcss';
    import { AppBar } from '@skeletonlabs/skeleton';

    onMount(() => {
        const ionicons = document.createElement('script');
        ionicons.type = 'module';
        ionicons.src = 'https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.esm.js';
        document.head.appendChild(ionicons);

        const ioniconsNoModule = document.createElement('script');
        ioniconsNoModule.setAttribute('nomodule', '');
        ioniconsNoModule.src = 'https://unpkg.com/ionicons@5.5.2/dist/ionicons/ionicons.js';
        document.head.appendChild(ioniconsNoModule);
    });
</script>

<main>
    <footer class="footer">
        <div class="waves">
            <div class="wave" id="wave1"></div>
            <div class="wave" id="wave2"></div>
            <div class="wave" id="wave3"></div>
            <div class="wave" id="wave4"></div>
        </div>
        <ul class="social-icon">
            <li class="social-icon__item">
                <a class="social-icon__link" href="#top">
                    <ion-icon name="logo-facebook"></ion-icon>
                </a>
            </li>
            <li class="social-icon__item">
                <a class="social-icon__link" href="#top">
                    <ion-icon name="logo-twitter"></ion-icon>
                </a>
            </li>
            <li class="social-icon__item">
                <a class="social-icon__link" href="#top">
                    <ion-icon name="logo-linkedin"></ion-icon>
                </a>
            </li>
            <li class="social-icon__item">
                <a class="social-icon__link" href="#top">
                    <ion-icon name="logo-instagram"></ion-icon>
                </a>
            </li>
        </ul>
        <ul class="menu">
            <li class="menu__item"><a class="menu__link" href="#top">Home</a></li>
            <li class="menu__item"><a class="menu__link" href="#top">About</a></li>
            <li class="menu__item"><a class="menu__link" href="#top">Services</a></li>
            <li class="menu__item"><a class="menu__link" href="#top">Team</a></li>
            <li class="menu__item"><a class="menu__link" href="#top">Contact</a></li>
        </ul>
        <p>&copy;2024 BedsMovers | All Rights Reserved</p>
    </footer>
</main>

<style type="postcss">
    @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap");

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: "Poppins", sans-serif;
    }

    .footer {
        position: relative;
        width: 100%;
        @apply bg-gradient-to-b from-primary-500 to-primary-900;
        min-height: 100px;
        padding: 20px 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }

    .social-icon,
    .menu {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        margin: 10px 0;
        flex-wrap: wrap;
    }

    .social-icon__item,
    .menu__item {
        list-style: none;
    }

    .social-icon__link {
        font-size: 2rem;
        color: #fff;
        margin: 0 10px;
        display: inline-block;
        transition: 0.5s;
    }

    .social-icon__link:hover {
        transform: translateY(-10px);
    }

    .menu__link {
        font-size: 1.2rem;
        color: #fff;
        margin: 0 10px;
        display: inline-block;
        transition: 0.5s;
        text-decoration: none;
        opacity: 0.75;
        font-weight: 300;
    }

    .menu__link:hover {
        opacity: 1;
    }

    .footer p {
        color: #fff;
        margin: 15px 0 10px 0;
        font-size: 1rem;
        font-weight: 300;
    }

    .waves {
        width: 100%;
    }

    .wave {
        position: absolute;
        top: -100px;
        left: 0;
        width: 100%;
        height: 100px;
        background: url("https://i.ibb.co/wQZVxxk/wave.png");
        background-size: 1000px 100px;
        opacity: 0;
        -webkit-filter: drop-shadow(0 1px 10px rgba(213, 1, 1, 0.8));
    }

    .wave#wave1 {
        z-index: 1000;
        bottom: 0;
        animation: animateWaves 4s linear infinite;
    }

    .wave#wave2 {
        z-index: 999;
        bottom: 10px;
        animation: animate 4s linear infinite !important;
    }

    .wave#wave3 {
        z-index: 1000;
        bottom: 15px;
        animation: animateWaves 3s linear infinite;
    }

    .wave#wave4 {
        z-index: 999;
        bottom: 20px;
        animation: animate 3s linear infinite;
    }

    @keyframes animateWaves {
        0% {
            background-position-x: 1000px;
        }
        100% {
            background-position-x: 0px;
        }
    }

    @keyframes animate {
        0% {
            background-position-x: -1000px;
        }
        100% {
            background-position-x: 0px;
        }
    }
</style>