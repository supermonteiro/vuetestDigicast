<template>
    <div class="app">
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

Vue.use(VueAxios, axios);

export default {
    name: 'App',
};
</script>

<style lang="scss">
body {
    color: #2c3e50;
    text-align: center;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}

a {
    margin-right: 10%;
}

nav {
    background-image: linear-gradient(-45deg, blue, lightblue);
    width: 50%;
    display: inline-block;
    text-align: center;
}

</style>
