<template>
    <div id="mainDiv">
        <form id="subForm" class="topBefore">
            <input id="name" type="text" placeholder="NAME">
            <input id="email" type="text" placeholder="E-MAIL">
            <textarea id="message" type="text" placeholder="MESSAGE"></textarea>
            <input id="submit" type="submit" value="GO!">
        </form>
    </div>
</template>

<script>
    // work in progress
    export default {
        name: "subForm"
    }

</script>

<style scoped>

    input::-webkit-input-placeholder, textarea::-webkit-input-placeholder {
        color: #aca49c;
        font-size: 0.875em;
    }

    input:focus::-webkit-input-placeholder, textarea:focus::-webkit-input-placeholder {
        color: #bbb5af;
    }

    input::-moz-placeholder, textarea::-moz-placeholder {
        color: #aca49c;
        font-size: 0.875em;
    }

    input:focus::-moz-placeholder, textarea:focus::-moz-placeholder {
        color: #bbb5af;
    }

    input::placeholder, textarea::placeholder {
        color: #aca49c;
        font-size: 0.875em;
    }

    input:focus::placeholder, textarea::focus:placeholder {
        color: #bbb5af;
    }

    input::-ms-placeholder, textarea::-ms-placeholder {
        color: #aca49c;
        font-size: 0.875em;
    }

    input:focus::-ms-placeholder, textarea:focus::-ms-placeholder {
        color: #bbb5af;
    }

    /* on hover placeholder */

    input:hover::-webkit-input-placeholder, textarea:hover::-webkit-input-placeholder {
        color: #e2dedb;
        font-size: 0.875em;
    }

    input:hover:focus::-webkit-input-placeholder, textarea:hover:focus::-webkit-input-placeholder {
        color: #cbc6c1;
    }

    input:hover::-moz-placeholder, textarea:hover::-moz-placeholder {
        color: #e2dedb;
        font-size: 0.875em;
    }

    input:hover:focus::-moz-placeholder, textarea:hover:focus::-moz-placeholder {
        color: #cbc6c1;
    }

    input:hover::placeholder, textarea:hover::placeholder {
        color: #e2dedb;
        font-size: 0.875em;
    }

    input:hover:focus::placeholder, textarea:hover:focus::placeholder {
        color: #cbc6c1;
    }

    input:hover::placeholder, textarea:hover::placeholder {
        color: #e2dedb;
        font-size: 0.875em;
    }

    input:hover:focus::-ms-placeholder, textarea:hover::focus:-ms-placeholder {
        color: #cbc6c1;
    }

    #subForm {
        width: 45vw;
    }

    #mainDiv {
        z-index: 2;
        position: absolute;
        display: flex;
        justify-content: center;
        align-content: center;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

    }
    #name {
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
    }
    input {
        font-size: 0.875em;
        width: 40vw;
        height: 10vh;
        padding: 0 15px 0 15px;
        background: transparent;
        outline: none;
        color: inherit;
        border: solid 1px #e4e1e1;
        border-bottom: none;
        transition: all 0.3s ease-in-out;
        -webkit-transition: all 0.3s ease-in-out;
        -moz-transition: all 0.3s ease-in-out;
        -ms-transition: all 0.3s ease-in-out;
    }

    #submit:hover, input:hover, textarea:hover {
        background: rgba(179,172, 167, 0.3);
        color: #e2dedb;
        backdrop-filter: blur(3px);
    }

    input[placeholder] {
        font-size: 1.5vw;
    }

    textarea {
        width: 40vw;
        height: 30vh;
        padding: 15px;
        background: transparent;
        outline: none;
        color: #efecec;
        font-size: 1.5vw;
        border: solid 1px #e4e1e1;
        transition: all 0.3s ease-in-out;
        -webkit-transition: all 0.3s ease-in-out;
        -moz-transition: all 0.3s ease-in-out;
        -ms-transition: all 0.3s ease-in-out;
    }

    #submit {
        width: 42.4vw;
        padding: 0;
        margin: -5px 0 0 0;
        font-size: 1.5vw;
        color: inherit;
        outline:none;
        cursor: pointer;
        border: solid 1px #e4e1e1;
        border-top: none;
        border-bottom-left-radius: 5px;
        border-bottom-right-radius: 5px;
    }

</style>