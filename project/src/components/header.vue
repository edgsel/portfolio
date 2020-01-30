<template>
    <div>
        <transition name="fade">
            <!--  almost implemented -->
            <nav id="nav" v-bind:style='{"background-color": (show ? "black" : "none" )}'>
                <ul>
                    <li class="bar"><router-link to="/">HOME</router-link></li>
                    <li class="bar"><router-link to="#whoAmI">WHO AM I?</router-link></li>
                    <li class="bar"><router-link to="#hobbies">HOBBIES</router-link></li>
                    <li class="bar"><router-link to="#contactMe">CONTACT ME</router-link></li>
                </ul>
            </nav>
        </transition>
    </div>

</template>

<script>
    import $ from 'jquery'
    export default {
        name: "app-header",

        data() {
            return {
                scrollPosition: null,
                show: false
            }
        },

        methods: {

            updateScroll() {
                this.scrollPosition = window.scrollY;
                this.show = this.scrollPosition >= 100 ? true : false;
                // eslint-disable-next-line no-console
                console.log(this.show)

            }
        },

        mounted() {
            window.addEventListener('scroll', this.updateScroll);
            $("#nav").delay(800).animate({right: '7px', opacity: '1'}, 1000);
        },
    }
    
</script>

<style scoped>
    #nav {
        display: flex;
        z-index: 1;
        position: fixed;
        justify-content: flex-end;
        font-weight: normal;
        list-style-type: none;
        font-size: 1.5vw;
        margin: 0;
        padding: 0;
        overflow: hidden;
        width: 100%;
        opacity: 0;
    }

    /*.navColor {*/

    /*    !*position: fixed;*!*/
    /*    z-index: 1;*/
    /*    background-color: red;*/
    /*    height: 100px;*/
    /*}*/

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
        /*border-bottom: 1px solid #ffffff;*/
        width: 0;
        left: 0;
        -webkit-transition: 0.5s ease;
        transition: 0.5s ease;
    }

    a {
        text-decoration: none;
        color: #ffffff
    }

   nav li .router-link-exact-active {
        content: '';
        display: block;
        border-bottom: 1px solid #ffffff;
        -webkit-transition: 0.5s ease;
        transition: 0.5s ease;
    }

   nav li .router-link-active {
       content: '';
       display: block;
       -webkit-transition: 0.5s ease;
       transition: 0.5s ease;
   }

    .bar:hover:after {
        width: 100%;
    }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .5s;
    }

</style>