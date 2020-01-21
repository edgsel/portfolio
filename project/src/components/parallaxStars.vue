<template>
    <div id="main">
<!--        <navigationBar></navigationBar>-->
        <div class="grid-container">
        </div>
    </div>
</template>

<script>
    // import navigationBar from './navigationBar';
    export default {
        name: "parallaxStars",
        components: {
            // navigationBar
        },

        methods: {
            createStars(quantity) {
                for (let i = 0; i < quantity; i++) {
                    let star = document.createElement('div');
                    star.classList.add('star', 'type-' + String(this.randomNumber(1,3)));
                    star.style.left = String(this.randomNumber(1,99) + '%');
                    star.style.bottom = String(this.randomNumber(1,99) + '%');
                    star.style.animationDuration = String(this.randomNumber(50,200) + 's');
                    document.getElementsByClassName("grid-container")[0].appendChild(star);
                }
            },

            randomNumber(min, max) {
                return Math.floor(Math.random() * max) + min;
            }
        },

        mounted() {
            this.createStars(150);
        }
    }
</script>

<style>
    body {
        margin: 0;
        padding: 0;
    }

    #main {
        margin-left: auto;
        margin-right: auto;
        overflow-x: hidden;
        overflow-y: hidden;
        background: radial-gradient(ellipse at bottom, #012950 0%, #000000 100%);
    }

    .grid-container {

        display: grid;
        position: relative;
        grid-template-rows: 1fr;
        width: 100vw;
        height: 100vh;
        /*min-height: 100vh;*/
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
    }

    .type-2 {
        width: 3px;
        height: 3px;
    }

    .type-3 {
        width: 4px;
        height: 4px;
    }


    @keyframes move {
        0% { transform: translateY(1000px); }
        100% {transform: translateY(-1000px); }
    }

</style>