<template>
    <div class="app">
        <link rel="stylesheet"
        href="https://use.fontawesome.com/releases/v5.2.0/css/all.css"
        integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ"
        crossorigin="anonymous">
        <nav>
            <router-link to="/">Home</router-link>
            <router-link to="/gallery">Gallery</router-link>
        </nav>
        <router-view/>
    </div>
</template>

<script>
import Vue from 'vue';
import axios from 'axios';
import VueAxios from 'vue-axios';
import { BootstrapVue, IconsPlugin } from 'bootstrap-vue';

Vue.use(VueAxios, axios, BootstrapVue, IconsPlugin);

export default {
    name: 'App',
};
</script>

<style lang="scss">
* {
    font-family: "Open Sans";
}

a {
    margin: 10%;
    color: lightblue;
    text-decoration: none;
}

body {
    color: #2c3e50;
    text-align: center;
    height: 100%;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

nav {
    background-image: linear-gradient(-45deg, blue, lightblue);
    width: 50%;
    display: inline-block;
    text-align: center;
    padding: 1% 0 1% 0;
}

.app {
    height: 100%;
}

.router-link-active {
    color: lightblue;
}

.router-link-exact-active {
    font-size: 18px;
    color: white;
}

</style>
