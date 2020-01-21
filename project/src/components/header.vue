<template>
    <nav id="nav">
        <ul class="navBar">
            <li class="bar"><router-link to="/">HOME</router-link></li>
            <li class="bar"><router-link to="#whoAmI">WHO AM I?</router-link></li>
            <li class="bar"><router-link to="#hobbies">HOBBIES</router-link></li>
            <li class="bar"><router-link to="#contactMe">CONTACT ME</router-link></li>
        </ul>
    </nav>
</template>

<script>
    import $ from 'jquery'
    export default {
        name: "header",

        mounted() {
            $(".navBar").delay(800).animate({right: '7px', opacity: '1'}, 1000);
        },
    }
    
</script>

<style scoped>
    #nav {
        display: flex;
        justify-content: flex-end;
        font-weight: normal;
        margin: 0;
        padding: 0;
        overflow: hidden;
    }

    .navBar {
        z-index: 1;
        position: absolute;
        list-style-type: none;
        overflow: hidden;
        font-size: 1.5vw;
        opacity: 0;
    }

    li {
        float: left;
        margin: 10px;
    }

    .bar {
        display: block;
        color: #ffffff;
        text-align: center;
        text-decoration: none;
    }

   .bar:after {
        content: '';
        display: block;
        border-bottom: 1px solid #ffffff;
        width: 0;
        left: 0;
        -webkit-transition: 0.5s ease;
        transition: 0.5s ease;
    }

    a {
        text-decoration: none;
        color: #ffffff
    }

    .router-link-exact-active {
        content: '';
        display: block;
        border-bottom: 1px solid #ffffff;
        -webkit-transition: 0.5s ease;
        transition: 0.5s ease;
    }

    .bar:hover:after {
        width: 100%;
    }

</style>