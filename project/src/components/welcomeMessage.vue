<template>
    <div>
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

<style>
    .screen-message {
        display: none;
        letter-spacing: -4px;
        font-weight: 100;
    }

</style>