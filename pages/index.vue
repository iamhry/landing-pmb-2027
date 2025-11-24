<template>
    <div>
        <Navbar :navlight="true" />

        <section class="relative md:py-24 py-16 bg-gradient-to-tr to-violet-950 via-violet-700 from-fuchsia-600">
            <div class="absolute inset-0 bg-no-repeat bg-top bg-cover opacity-20"
                :style="{ backgroundImage: `url(${bg})` }"></div>
            <div class="container relative">
                <div class="grid grid-cols-1 text-center mt-12">
                    <span class="text-yellow-400 font-semibold mb-3 uppercase">#Kampus_Sehat_Mencerahkan</span>
                    <h1
                        class="font-bold lg:leading-normal leading-normal tracking-wide text-4xl lg:text-5xl text-white mb-5">
                        Pendaftaran Mahasiswa Baru
                        <br>2026/2027
                    </h1>
                    <p class="text-white/50 text-lg max-w-xl mx-auto">Setiap mimpi butuh tempat untuk tumbuh.
                        Temukan tempat itu di Universitas Muhammadiyah PKU Surakarta.</p>

                    <div class="mt-6">
                        <NuxtLink to="https://admission.umpku.ac.id/site/landing" target="_blank"
                            class="h-12 px-6 tracking-wide inline-flex items-center justify-center font-medium rounded-md bg-yellow-500 text-white">
                            Daftar Sekarang <i class="mdi mdi-arrow-right align-middle ms-1"></i></NuxtLink>
                    </div>
                </div>
            </div>

            <div class="container-fluid relative mt-10">
                <div class="grid grid-cols-5 items-center lg:gap-4 md:gap-2 gap-1 xl:mx-36 mx-3">
                    <div>
                        <img :src="home1" class="rounded-md shadow shadow-white/30" alt="" />
                    </div>

                    <div class="grid md:grid-cols-1 grid-cols-1 lg:gap-4 md:gap-2 gap-1">
                        <div>
                            <img :src="home2" class="rounded-md shadow shadow-white/30" alt="" />
                        </div>

                        <div>
                            <img :src="home3" class="rounded-md shadow shadow-white/30" alt="" />
                        </div>
                    </div>

                    <div>
                        <img :src="home4" class="rounded-md shadow shadow-white/30" alt="" />
                    </div>

                    <div class="grid md:grid-cols-1 grid-cols-1 lg:gap-4 md:gap-2 gap-1">
                        <div>
                            <img :src="home5" class="rounded-md shadow shadow-white/30" alt="" />
                        </div>

                        <div>
                            <img :src="home6" class="rounded-md shadow shadow-white/30" alt="" />
                        </div>
                    </div>

                    <div>
                        <img :src="home7" class="rounded-md shadow shadow-white/30" alt="" />
                    </div>
                </div>
            </div>
        </section>

        <section class="relative md:py-24 py-16">
            <div class="container relative lg:mt-18 mt-16">
                <div class="grid grid-cols-1 pb-6 text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Informasi Pendaftaran</span>
                    <h4 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Mudah, Cepat,
                        dan Terjangkau untuk Semua</h4>
                    <p class="text-slate-400 max-w-xl mx-auto">Proses daftar di sini gampang banget. Tinggal cek
                        syaratnya, ikuti alurnya, dan kamu langsung bisa mulai kuliah.</p>
                </div>
                <div class="grid md:grid-cols-12 grid-cols-1 items-center gap-6">
                    <FaqAbout />
                    <div class="lg:col-span-6 md:col-span-5">
                        <Syarat />
                    </div>
                </div>
            </div>
            <section class="pt-6">
                <div class="grid grid-cols-1 pb-8 text-center">
                    <h3 class=" mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">
                        Mitra Kami
                    </h3>
                </div>
                <PartnerMitraIndex />

                <div class="grid md:grid-cols-12 grid-cols-1 mt-6">
                    <div class="md:col-span-12 text-center">
                        <NuxtLink to="/mitra"
                            class="text-slate-400 hover:text-violet-600 duration-500 ease-in-out font-medium inline-flex items-center">
                            Lihat Mitra Lainnya
                            <i class="mdi mdi-arrow-right align-middle ml-2"></i>
                        </NuxtLink>
                    </div>
                </div>
            </section>

            <!-- <div class="container relative md:mt-24 mt-16">
                <AboutOne :title="true" />
            </div> -->

            <div class="container relative md:mt-24 mt-16">
                <div class="grid grid-cols-1  text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Berita & Event PMB</span>
                    <h4 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Info PMB
                        Terbaru</h4>
                    <p class="text-slate-400 max-w-xl mx-auto">Jangan lewatkan berita, pengumuman, dan agenda penting
                        seputar Penerimaan Mahasiswa Baru (PMB). Temukan informasi terkini, tips pendaftaran, dan event
                        kampus untuk mempersiapkan langkah terbaikmu.</p>
                </div>

                <!-- <div class="grid grid-cols-1 relative mt-3">
                    <ClientOnly>
                        <CoursesSlider />
                    </ClientOnly>
                </div> -->

                <div class="grid md:grid-cols-12 grid-cols-1 mt-6">
                    <div class="md:col-span-12 text-center">
                        <NuxtLink to="/" class="text-slate-400 hover:text-violet-600 duration-500 ease-in-out">Lihat
                            Berita Lainnya <i class="mdi mdi-arrow-right align-middle"></i></NuxtLink>
                    </div>
                </div>
            </div>

            <!-- <div class="container relative">
                <div class="grid grid-cols-1 pb-6 text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Categories</span>
                    <h4 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Explore 1500+
                        Free Education Courses</h4>

                    <p class="text-slate-400 max-w-xl mx-auto">Discover a world of knowledge and opportunities with our
                        online education platform pursue a new career.</p>
                </div>

                <Categories />
            </div> -->

        </section>
        <!-- <ClientOnly>
            <CtaOne />
        </ClientOnly> -->

        <section class="relative lg:pb-12 py-0">
            <!-- <div class="container relative">
                <div class="grid grid-cols-1 pb-6 text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Teachers</span>
                    <h4 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Expert
                        Instructors</h4>
                    <p class="text-slate-400 max-w-xl mx-auto">Discover a world of knowledge and opportunities with our
                        online education platform pursue a new career.</p>
                </div>
                <ExpertTeam />
            </div> -->

            <div class="container relative lg:mt-0 mb-10 mt-5">
                <div class="grid grid-cols-1 pb-10 text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Testimoni Alumni</span>
                    <h3 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Apa Kata
                        Mereka?</h3>
                    <!-- <p class="text-slate-400 max-w-xl mx-auto">Discover a world of knowledge and opportunities with our
                        online education platform pursue a new career.</p> -->
                </div>
                <ClientOnly>
                    <Alumni />
                </ClientOnly>
            </div>

        </section>

        <Footer />

        <Switcher />

        <ScrollToTop />
    </div>
</template>

<script setup>
import PartnerMitraIndex from '~/components/partner-mitra-index.vue'
import bg from '@/assets/images/bg/bg.png'
import home1 from '@/assets/images/team/img-1.jpg'
import home2 from '@/assets/images/team/img-2.jpg'
import home3 from '@/assets/images/team/img-3.jpg'
import home4 from '@/assets/images/team/img-4.jpg'
import home5 from '@/assets/images/team/img-12.jpg'
import home6 from '@/assets/images/team/img-5.jpg'
import home7 from '@/assets/images/team/img-8.jpg'
import Syarat from '~/components/syarat.vue'
</script>
