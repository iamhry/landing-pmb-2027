<template>
    <div>
        <Navbar />
        <section class="relative md:py-24 py-16 ">
            <div class="container relative pt-10 mt-15">
                <div class="grid grid-cols-1  text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Pendaftaran</span>
                    <h4 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Biaya
                        Pendaftaran</h4>
                    <p class="text-slate-400 max-w-xl mx-auto">Biaya pendaftaran PMB UMPKU Tahun 2026/2027 tersedia
                        dalam dua jalur: Reguler & Alih Jenjang/RPL.
                        Pilih jalur sesuai kebutuhanmu dan mulai langkah pertama menuju kampus impian!</p>
                </div>
                <Pendaftaran />
            </div>
        </section>

        <Footer />
        <ScrollToTop />
        <Switcher />
    </div>
</template>

<script setup>
import VueTypewriterEffect from "vue-typewriter-effect";
import bg from '@/assets/images/bg/4.jpg'
import map from '@/assets/images/map.svg'
</script>
