<template>
    <nav id="topnav" class="defaultscroll is-sticky" :class="tagline ? 'tagline-height' : ''">
        <div class="container relative">

            <NuxtLink v-if="navlight" class="logo" width="130" to="/">
                <span class="inline-block dark:hidden">
                    <img :src="logoDark" class="l-dark w-130" height="24" alt="" />
                    <img :src="logoLight" class="l-light w-130" height="24" alt="" />
                </span>
                <img :src="logoLight" width="130" height="20" class="hidden dark:inline-block" alt="" />
            </NuxtLink>

            <NuxtLink v-if="!navlight" class="logo" to="/">
                <img :src="logoDark" class="inline-block dark:hidden" alt="" />
                <img :src="logoLight" class="hidden dark:inline-block" alt="" />
            </NuxtLink>

            <div class="menu-extras">
                <div class="menu-item">
                    <NuxtLink :to="[]" class="navbar-toggle" :class="toggle ? 'open' : ''" id="isToggle"
                        @click="toggleMenu">
                        <div class="lines">
                            <span></span>
                            <span></span>
                            <span></span>
                        </div>
                    </NuxtLink>
                </div>
            </div>

            <!--Login button Start-->
            <ul class="buy-button list-none mb-0">
                <!-- <li class="inline-block relative">
                    <button v-if="navlight" class="text-[20px]" @click="searchMenu = !searchMenu" type="button">
                        <i class="iconoir-search align-middle login-btn-primary"></i>
                        <i class="iconoir-search text-white align-middle login-btn-light"></i>
                    </button>          
                    <button v-if="!navlight" class="text-[20px]" @click="searchMenu = !searchMenu" type="button">
                        <i class="iconoir-search align-middle"></i>
                    </button>      

                    <div class="fixed w-full h-[100vh] top-0 left-0 flex justify-center" style="background-color: rgba(0, 0, 0, 0.5);" :class="searchMenu ? '' : 'hidden'">
                        <div id="" class="rounded-md shadow dark:shadow-gray-800 bg-white dark:bg-slate-900 text-slate-900 dark:text-white w-11/12 max-w-5xl mt-20 fixed">
                            <div class="relative w-full h-auto">
                                <form method="dialog" class="modal-backdrop">
                                    <button class="size-5 rounded-md flex justify-center items-center absolute top-0 end-0 btn-ghost" @click="searchMenu = !searchMenu"><i data-feather="x" class="size-4"></i></button>
                                </form>
                                <div class="p-6 text-center">
                                    <form class="relative">
                                        <i class="iconoir-search text-lg absolute top-2.5 end-0"></i>
                                        <input type="text" class="w-full py-2 px-3 bg-transparent focus:outline-none rounded-md pe-6 h-10" name="s" id="searchItem" placeholder="Search...">
                                    </form>
                                </div>
                            </div>
                        </div>
                    </div> 
                </li> -->

                <!-- <li class="dropdown inline-block relative mx-1">
                    <button class="dropdown-toggle size-8 inline-flex items-center justify-center tracking-wide align-middle duration-500 text-base text-center rounded-full bg-violet-600 border border-violet-600 text-white" type="button" @click="cart = !cart">
                        <i data-feather="shopping-cart" class="size-4"></i>
                    </button>
                    <div class="dropdown-menu absolute end-0 m-0 mt-4 z-10 w-60 rounded-md bg-white dark:bg-slate-900 shadow dark:shadow-gray-800" :class="cart ? '' : 'hidden'">
                        <ul class="py-3 text-start" aria-labelledby="dropdownDefault">
                            <li class="px-3">Your shopping cart is empty.</li>
                        </ul>
                    </div>


                </li> -->
                <li class="inline-block relative">
                    <NuxtLink to="https://admission.umpku.ac.id/" target="_blank"
                        class=" inline-flex items-center justify-center px-4 py-2 text-white bg-violet-600 hover:bg-violet-700 rounded-md transition duration-300">
                        <i data-feather="log-in" class="size-4 me-2"></i>Login
                    </NuxtLink>
                </li>
                <!-- <li class="dropdown inline-block relative">
                    <button @click="userAccount = !userAccount" class="dropdown-toggle items-center" type="button">
                        <span
                            class="size-8 inline-flex items-center justify-center tracking-wide align-middle duration-500 text-base text-center rounded-full bg-violet-600 border border-violet-600 text-white"><img
                                :src="user" class="rounded-full size-[30px]" alt="" /></span>
                    </button>

                    <div class="dropdown-menu absolute end-0 m-0 mt-4 z-10 w-44 rounded-md overflow-hidden bg-white dark:bg-slate-900 shadow dark:shadow-gray-700"
                        :class="userAccount ? '' : 'hidden'">
                        <ul class="py-2 text-start">
                            <li>
                                <NuxtLink :to="[]"
                                    class="flex items-center font-medium py-2 px-4 dark:text-white/70 hover:text-violet-600 dark:hover:text-white">
                                    <i data-feather="user" class="size-4 me-2"></i>Profile</NuxtLink>
                            </li>
                            <li>
                                <NuxtLink :to="[]"
                                    class="flex items-center font-medium py-2 px-4 dark:text-white/70 hover:text-violet-600 dark:hover:text-white">
                                    <i data-feather="settings" class="size-4 me-2"></i>Settings</NuxtLink>
                            </li>
                            <li class="border-t border-gray-100 dark:border-gray-800 my-2"></li>
                            <li>
                                <NuxtLink :to="[]"
                                    class="flex items-center font-medium py-2 px-4 dark:text-white/70 hover:text-violet-600 dark:hover:text-white">
                                    <i data-feather="lock" class="size-4 me-2"></i>Lockscreen</NuxtLink>
                            </li>
                            <li>
                                <NuxtLink :to="[]"
                                    class="flex items-center font-medium py-2 px-4 dark:text-white/70 hover:text-violet-600 dark:hover:text-white">
                                    <i data-feather="log-out" class="size-4 me-2"></i>Logout</NuxtLink>
                            </li>
                        </ul>
                    </div>
                </li> -->
            </ul>

            <div id="navigation" :class="toggle ? 'block' : 'none'">

                <ul class="navigation-menu justify-start" :class="navlight ? 'nav-light' : ''">
                    <li :class="current === '/' ? 'active' : ''">
                        <NuxtLink to="/" class="sub-menu-item">Home</NuxtLink>
                    </li>
                    <li :class="current === '/program-studi' ? 'active' : ''">
                        <NuxtLink to="/program-studi" class="sub-menu-item">Program Studi</NuxtLink>
                    </li>
                    <li class="has-submenu parent-parent-menu-item"
            :class="['/biaya-pendaftaran', '/biaya-studi'].includes(current) ? 'active' : ''">
            
            <NuxtLink :to="[]" @click="submenu('biaya-menu')">Biaya</NuxtLink>
            <span class="menu-arrow" @click="submenu('biaya-menu')"></span>
            
            <ul class="submenu" :class="openMenu === 'biaya-menu' ? 'open' : ''"> 
                <li :class="current === '/biaya-pendaftaran' ? 'active' : ''">
                    <NuxtLink to="/biaya-pendaftaran" class="sub-menu-item">Biaya Pendaftaran</NuxtLink>
                </li>
                <li :class="current === '/biaya-studi' ? 'active' : ''">
                    <NuxtLink to="/biaya-studi" class="sub-menu-item">Biaya Studi</NuxtLink>
                </li>
            </ul>
        </li>

        <li class="has-submenu parent-parent-menu-item"
            :class="['/mitra', '/faq-umpku'].includes(current) ? 'active' : ''">
            
            <NuxtLink :to="[]" @click="submenu('informasi-menu')">Informasi</NuxtLink>
            <span class="menu-arrow" @click="submenu('informasi-menu')"></span>
            
            <ul class="submenu" :class="openMenu === 'informasi-menu' ? 'open' : ''">
                <li class="parent-menu-item">
                    <NuxtLink to="https://docs.google.com/forms/d/e/1FAIpQLSeh5QpqEXVIBBvKcGbQALWFpfknIEMuQHvttzzT83hJTpW0yg/viewform?pli=1">Evaluasi</NuxtLink>
                </li>
                <li :class="current === '/mitra' ? 'active' : ''" class="parent-menu-item">
                    <NuxtLink to="/mitra">Mitra</NuxtLink>
                </li>
                <li :class="current === '/faq-umpku' ? 'active' : ''" class="parent-menu-item">
                    <NuxtLink to="/faq-umpku">FAQ</NuxtLink>
                </li>
            </ul>
        </li>

                    <li :class="current === '/beasiswa' ? 'active' : ''">
                        <NuxtLink to="/beasiswa" class="sub-menu-item">Beasiswa</NuxtLink>
                    </li>
                    <li :class="current === '/brosur' ? 'active' : ''">
                        <NuxtLink to="/brosur" class="sub-menu-item">Brosur</NuxtLink>
                    </li>
                     <li :class="current === '/kontak' ? 'active' : ''">
                        <NuxtLink to="/kontak" class="sub-menu-item">Kontak</NuxtLink>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script setup>
import { useRoute } from 'vue-router'
import feather from 'feather-icons'

import logoDark from '@/assets/images/logo/logo-1.png'
import logoLight from '@/assets/images/logo/logo-2.png'
import user from '@/assets/images/team/1.jpg'
import demo1 from '@/assets/images/demos/1.png'
import demo2 from '@/assets/images/demos/2.png'
import demo3 from '@/assets/images/demos/3.png'
import demo4 from '@/assets/images/demos/4.png'
import demo5 from '@/assets/images/demos/5.png'

defineProps({
    navlight: Boolean,
    tagline: Boolean
})

const router = useRoute();
const current = ref(router.path);
const openMenu = ref('')
const toggle = ref(false);
const cart = ref(false);
const userAccount = ref(false)
const searchMenu = ref(false)

onMounted(() => {
    feather.replace();
    window.addEventListener('scroll', handleScroll);
    window.scrollTo(0, 0)
})

onUnmounted(() => {
    window.removeEventListener('scroll', handleScroll);
})

const submenu = (item) => {
    openMenu.value = item
}

const toggleMenu = () => {
    toggle.value = !toggle.value
}

const handleScroll = () => {
    const navbar = document.getElementById("topnav");
    if (
        document.body.scrollTop >= 50 ||
        document.documentElement.scrollTop >= 50
    ) {
        navbar.classList.add("nav-sticky");
    } else {
        navbar.classList.remove("nav-sticky");
    }
}
</script>
