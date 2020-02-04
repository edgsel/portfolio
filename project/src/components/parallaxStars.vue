<template>
    <div id="main">
        <div class="grid-container"></div>
    </div>
</template>

<script>

    export default {
        name: "parallaxStars",

        methods: {
            createStars(quantity) {
                for (let i = 0; i < quantity; i++) {
                    let star = document.createElement('div');
                    star.classList.add('star', 'type-' + String(this.randomNumber(1,3)));
                    star.style.left = String(this.randomNumber(1,99) + '%');
                    star.style.bottom = String(this.randomNumber(1,200) + '%');
                    star.style.animationDuration = String(this.randomNumber(50,200) + 's');
                    document.getElementsByClassName("grid-container")[0].appendChild(star);
                }
            },

            randomNumber(min, max) {
                return Math.floor(Math.random() * max) + min;
            }
        },

        mounted() {
            this.createStars(170);
        }
    }
</script>

<style>

    body {
        margin: 0;
        padding: 0;
    }

    #main {
        z-index: 2;
        margin-left: auto;
        margin-right: auto;
        overflow: hidden;
        background: radial-gradient(ellipse at bottom, #012950 0%, #000000 100%);
        background-size: cover;
    }

    .grid-container {
        display: grid;
        position: relative;
        grid-template-rows: 1fr;
        width: 100vw;
        height: 100vh;
        align-items: start;
    }

    .star {
        position: absolute;
        background: white;
        border-radius: 50px;
        animation: move;
        animation-iteration-count: infinite;
        animation-timing-function: linear;
    }

    .type-1 {
        width: 1px;
        height: 1px;
        transition: 0.5s;
    }

    .type-2 {
        width: 3px;
        height: 3px;
        transition: 0.5s;
    }

    .type-3 {
        width: 4px;
        height: 4px;
        transition: 0.5s;
    }
    
    @keyframes move {
        0% { transform: translateY(1000px); }
        100% {transform: translateY(-1000px); }
    }

</style>