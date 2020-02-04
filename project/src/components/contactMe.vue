<template>
    <div>
        <submission-form></submission-form>
        <parallax-stars></parallax-stars>
    </div>
</template>

<script>
    import parallaxStars from "./parallaxStars";
    import submissionForm from "./submissionForm.vue"
    export default {
        name: "contactMe",
        components: {
            parallaxStars,
            submissionForm
        }
    }
</script>

<style scoped>

</style>