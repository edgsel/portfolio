<template>
    <div id="nav">
        <ul class="navBar">
            <li><a class="bar active" href="#home">HOME</a></li>
            <li><a class="bar" href="#whoAmI">WHO AM I?</a></li>
            <li><a class="bar" href="#hobbies">HOBBIES</a></li>
            <li><a class="bar" href="#contactMe">CONTACT ME</a></li>
        </ul>
    </div>
</template>

<script>
    import $ from 'jquery'

    export default {
        name: "navigationBar",

        mounted() {
            $(".navBar").delay(800).animate({right: '7px', opacity: '1'}, 1000);
            /* not implemented yet */
            // setTimeout(function () {
            //     $(".active").after(function () {
            //         $(".active").animate({width: "100%"}, 1000);
            //     });
            // }, 1500);
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
    }

    .bar {
        display: block;
        color: #ffffff;
        text-align: center;
        text-decoration: none;
    }

    .active:after, .bar:after {
        content: '';
        display: block;
        border-bottom: 1px solid #ffffff;
        width: 0;
        left: 0;
        -webkit-transition: 0.5s ease;
        transition: 0.5s ease;
    }
    .active:after {
        width:0%;
    }

    .bar:hover:after {
        width: 100%;
    }


</style>