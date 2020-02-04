<template>
    <div>
        <welcome-message></welcome-message>
        <parallax-stars></parallax-stars>
    </div>
</template>

<script>
    import parallaxStars from "./parallaxStars";
    import welcomeMessage from "./welcomeMessage";

    export default {
        name: "home",
        components: {
            parallaxStars,
            welcomeMessage
        }
    }
</script>

<style scoped>

</style>