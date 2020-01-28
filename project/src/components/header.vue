<template>
    <div>
        <div id="blurry-scroll"></div>
        <nav id="nav">
            <ul>
                <li class="bar"><router-link to="/">HOME</router-link></li>
                <li class="bar"><router-link to="#whoAmI">WHO AM I?</router-link></li>
                <li class="bar"><router-link to="#hobbies">HOBBIES</router-link></li>
                <li class="bar"><router-link to="#contactMe">CONTACT ME</router-link></li>
            </ul>
        </nav>
    </div>
</template>

<script>
    import $ from 'jquery'
    export default {
        name: "app-header",

        methods: {
            // not implemented yet. In progress.
            changeNavbarColorOnScroll() {
                let ref = this;
                let scroll = $(window).scrollTop();
                $(window).scroll(function () {
                    // let scroll = $(window).scrollTop();
                    // eslint-disable-next-line no-console
                    console.log(scroll);
                    if (scroll >= 200) ref.animateColorOfNav(1);

                    if (scroll <= 100) ref.animateColorOfNav(0);
                  })
              },

            animateColorOfNav(opac) {
                $("#blurry-scroll").animate({opacity: opac}, 300);
            }
        },

        mounted() {
            this.changeNavbarColorOnScroll();
            $("#nav").delay(800).animate({right: '7px', opacity: '1'}, 1000);
        },
    }
    
</script>

<style scoped>

    #blurry-scroll {
        top:0; left: 0;
        width: 100%;
        height: 6.5rem;
        overflow: hidden;
        position: fixed;
        opacity: 0;
        /*filter: blur(2px);*/
        background-color: #012965;
        /*opacity: 0.01;*/
    }

    /*nav {*/
    /*    @extend #blurry-scroll;*/
    /*    filter: none;*/
    /*}*/

    nav {
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