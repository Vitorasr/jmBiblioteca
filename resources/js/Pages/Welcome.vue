<template>
    <div>
        <Navbar :activePage="currentPage" />
        <Banner/>
        <Arrival/>
        <Books/>
        <Footer/>
    </div>
</template>

<script setup>
import { Head, Link } from '@inertiajs/vue3';
import Navbar from '../Components/Navbar.vue';
import Banner from '../Components/Banner.vue';
import Arrival from '../Components/Arrival.vue';
import Books from '../Components/Books.vue';
import Footer from '../Components/Footer.vue';


import { ref } from 'vue';

const currentPage = ref(window.location.pathname);
</script>