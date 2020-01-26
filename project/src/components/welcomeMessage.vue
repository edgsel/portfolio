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
                screenMessages: ["hi stranger", "welcome to my page","explore and..." ,"enjoy "]
            }
        },

        mounted() {
            // unfortunately, jquery method implemented, no solution for transition group w/o click event.
            let h1 = $(".screen-message");
            let messages = this.screenMessages;
            let quoteIndex = -1;

            function showNextMessage() {
                if (quoteIndex >= messages.length - 1) {
                    quoteIndex = -1;
                }

                ++quoteIndex;
                // recursively call function again when animation is done
                h1.text(messages[quoteIndex])
                    .fadeIn(2000)
                    .delay(3000)
                    .fadeOut(2000, showNextMessage);
            }

            setTimeout(showNextMessage, 2000);
        }
    }
</script>

<style >
    .screen-message {
        display: none;
        letter-spacing: -4px;
        font-weight: 100;
    }
</style>