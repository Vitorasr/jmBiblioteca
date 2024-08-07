<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light fixed-top">
        <div class="container-fluid">
            <a class="navbar-brand" href="/">Biblioteca Jm</a>
            <button class="navbar-toggler" type="button" @click="toggleNavbar" aria-controls="navbarNav"
                aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div :class="['collapse navbar-collapse', { show: isNavbarOpen }]">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" :class="{ active: isActive('/') }" aria-current="page" href="/">
                            Home
                            <span :class="{ 'underline': isActive('/') }"></span>
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" :class="{ active: isActive('/about') }" href="/about">
                            About
                            <span :class="{ 'underline': isActive('/about') }"></span>
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" :class="{ active: isActive('/services') }" href="/services">
                            Services
                            <span :class="{ 'underline': isActive('/services') }"></span>
                        </a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" :class="{ active: isActive('/contact') }" href="/contact">
                            Contact
                            <span :class="{ 'underline': isActive('/contact') }"></span>
                        </a>
                    </li>
                </ul>
                <button class="btn btn-primary" type="button">
                    Get started
                </button>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { ref, defineProps } from 'vue';

const props = defineProps({
    activePage: {
        type: String,
        required: true,
    },
});

const isNavbarOpen = ref(false);

function toggleNavbar() {
    isNavbarOpen.value = !isNavbarOpen.value;
}

function isActive(href) {
    return props.activePage === href;
}
</script>

<style scoped>
.underline {
    position: relative;
}

.underline::after {
    content: '';
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    background-color: #eab308;
    transition: all 0.3s ease;
}

.nav-link:hover .underline::after,
.nav-link.active .underline::after {
    width: 100%;
}
</style>