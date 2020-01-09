<template>
    <div id="nav">
        <ul class="navBar">
            <li><a href="#home">HOME</a></li>
            <li><a href="#whoAmI">WHO AM I?</a></li>
            <li><a href="#hobbies">HOBBIES</a></li>
            <li><a href="#contactMe">CONTACT ME</a></li>
        </ul>
    </div>
</template>

<script>
    import $ from 'jquery'

    export default {
        name: "navigationBar",

        mounted() {
            $(".navBar").delay(1000).animate({right: '7px', opacity: '1'}, 1000);
        }
    }

</script>

<style>

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
        /*right: 10px;*/
    }

    li a {
        display: block;
        color: #ebebeb;
        /*opacity: 0.8;*/
        text-align: center;
        text-decoration: none;
    }

</style>