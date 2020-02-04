<template>
    <div id="message">
        <h1 class="screen-message"></h1>
    </div>
</template>

<script>
    import $ from 'jquery'

    export default {
        name: "welcomeMessage",

        data() {
            return {
                screenMessages: ["hi stranger", "welcome to my page","explore it" ,"enjoy it"]
            }
        },

        mounted() {
            // unfortunately, jquery method implemented, no solution for transition group w/o click event found
            let h1 = $(".screen-message");
            let messages = this.screenMessages;
            let quoteIndex = -1;

            function showNextMessage() {
                let fadeDelay = 1500;

                if (quoteIndex >= messages.length - 1)  quoteIndex = -1;

                ++quoteIndex;

                if (messages[quoteIndex] === messages[messages.length - 1])  fadeDelay = 4000;
                // recursively call function again when animation is done
                h1.text(messages[quoteIndex])
                    .fadeIn(2500)
                    .delay(1000)
                    .fadeOut(fadeDelay, showNextMessage);
            }

            setTimeout(showNextMessage, 2000);
        }
    }
</script>

<style scoped>
    #message {
        z-index: 2;
        display: flex;
        position: absolute;
        justify-content: center;
        vertical-align: center;
        align-items: center;
        text-align: center;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 4.5vw
    }

    .screen-message {
        display: none;
        letter-spacing: -4px;
        font-weight: 100;
    }

</style>