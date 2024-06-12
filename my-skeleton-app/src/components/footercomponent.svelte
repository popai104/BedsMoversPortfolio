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
    <div class="footer">
        <ul class="social-icon">
            <li class="social-icon__item">
                <a class="social-icon__link" href="#top">
                    <ion-icon name="logo-youtube"></ion-icon>
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
        <p>&copy;2024 BedsMovers | All Rights Reserved</p>
    </div>

</main>

<style type="postcss">
    @import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800;900&display=swap");

    main {
        min-height: calc(0-100vh); /* 100px is the min-height of the footer */
    }
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }
    .footer {
        width: 100%;
        opacity: 1;
        min-height: 100px;
        padding: 10px 50px;
        padding-top: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
    .social-icon,
    .social-icon__item,
    .social-icon__link {
        opacity: 1;
        font-size: 2rem;
        color: #fff;
        margin: 0 10px;
        display: inline-block;
        transition: 0.5s;
        -webkit-filter: drop-shadow(0 1px 10px rgba(255, 255, 255, 0.1));
    }
    .social-icon__link:hover {
        transform: translateY(-15px);
        -webkit-filter: drop-shadow(0 1px 8px rgba(255, 255, 255, 1));
    }
    .footer p {
        color: #fff;
        margin: 15px 0 10px 0;
        font-size: 1rem;
        font-weight: 300;
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