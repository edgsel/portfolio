<template>
    <div id="nav">
        <ul class="navBar">
            <li><a @click="setActive('home')" v-bind:class="{active: isActive('home')}" class="bar" href="#home">HOME</a></li>
            <li><a @click="setActive('whoAmI')" v-bind:class="{active: isActive('whoAmI')}" class="bar" href="#whoAmI">WHO AM I?</a></li>
            <li><a @click="setActive('hobbies')" v-bind:class="{active: isActive('hobbies')}" class="bar" href="#hobbies">HOBBIES</a></li>
            <li><a @click="setActive('contactMe')" v-bind:class="{active: isActive('contactMe')}" class="bar" href="#contactMe">CONTACT ME</a></li>
        </ul>
<!--        <nav class="navBar">-->
<!--            <router-link></router-link>-->
<!--        </nav>-->
    </div>
</template>

<script>
    import $ from 'jquery'

    export default {
        name: "navigationBar",

        data: function() {
            return { activeItem: 'home'}
        },

        mounted() {
            $(".navBar").delay(800).animate({right: '7px', opacity: '1'}, 1000);
        },

        methods: {
            isActive(menuItem) {
                return this.activeItem === menuItem
            },
            setActive(menuItem) {
                this.activeItem = menuItem
            }

        }
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
        width:100%;
        /*border-bottom: 2px solid #ffffff;*/
        transition: .5s;
    }

    .bar:hover:after {
        width: 100%;
    }


</style>