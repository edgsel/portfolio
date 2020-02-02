<template>
    <div>
        <!--  almost implemented -->
        <nav id="nav" v-bind:class = "[show ? 'colorNav' : 'deleteColorNavSmoothly']">
            <div class="test">
                <ul>
                    <li class="bar"><router-link to="/">HOME</router-link></li>
                    <li class="bar"><router-link to="#whoAmI">WHO AM I?</router-link></li>
                    <li class="bar"><router-link to="#hobbies">HOBBIES</router-link></li>
                    <li class="bar"><router-link to="#contactMe">CONTACT ME</router-link></li>
                </ul>
            </div>
        </nav>
    </div>

</template>

<script>
    import $ from 'jquery'
    export default {
        name: "app-header",

        data() {
            return {
                show: false
            }
        },

        methods: {

            updateScroll() {
                this.scrollPosition = window.scrollY;
                this.show = this.scrollPosition >= 100;
            },
        },

        mounted() {
            window.addEventListener('scroll', this.updateScroll);
            $(".test").delay(800).animate({"padding-right": '7px', opacity: '1'}, 1000);
        }
    }
    
</script>

<style scoped>
    #nav {
        display: flex;
        z-index: 1;
        position: fixed;
        justify-content: flex-end;
        font-weight: 300;
        list-style-type: none;
        font-size: 1.5vw;
        padding-bottom: 15px;
        top:0;
        overflow: hidden;
        width: 100%;
    }

    .test {
        opacity: 0;
    }

    .colorNav {
        background-color: rgba(1, 30, 60, 0.6);
        height: inherit;
        transition: 0.3s;
        backdrop-filter: blur(2px); /* works in chrome, safari perfectly */
    }

    .deleteColorNavSmoothly {
        background-color: transparent;
        transition: 0.3s;
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

    @media screen and (max-width: 768px) {
        #nav {
            padding-bottom: 0;
        }
    }

</style>