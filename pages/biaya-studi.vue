<template>
    <div>
        <Navbar />
        <section class="relative md:py-24 py-16 ">
            <div class="container relative pt-10 mt-15">
                <div class="grid grid-cols-1 text-center">
                    <span class="text-violet-600 font-semibold mb- uppercase">Biaya Studi</span>
                    <h4 class="mb-1 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">
                        🎓 Kuliah di UMPKU? <br>
                        Gak perlu mahal-mahal, kok!
                    </h4>
                    <p class="text-slate-400 max-w-xl mb-6 mx-auto">✨ Dari yang hemat sampai jurusan favorit, semua ada
                        rinciannya.</p>
                </div>
                <div class="relative overflow-x-auto shadow-xl dark:shadow-gray-700 sm:rounded-lg">
                    <table class="w-full text-sm text-left text-gray-500 dark:text-gray-400">
                        <thead class="text-xs text-white uppercase bg-violet-600 dark:bg-violet-700">
                            <tr>
                                <th scope="col" class="px-4 py-3 font-bold tracking-wider rounded-tl-lg">
                                    🎓 Program Studi
                                </th>
                                <th scope="col" class="px-4 py-3 font-bold tracking-wider text-center">
                                    Cicilan UKT 1 (Awal Semester)
                                </th>
                                <th scope="col" class="px-4 py-3 font-bold tracking-wider text-center">
                                    Cicilan UKT 2 (Tengah Semester)
                                </th>
                                <th scope="col" class="px-4 py-3 font-bold tracking-wider text-right rounded-tr-lg">
                                    Total UKT / Semester
                                </th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(item, index) in biayaUkt" :key="index"
                                :class="[item.bgClass, 'border-b dark:border-gray-700 hover:bg-gray-100 dark:hover:bg-gray-800/50 transition duration-300']">

                                <th scope="row"
                                    class="px-4 py-3 font-medium text-gray-900 whitespace-nowrap dark:text-white">
                                    {{ item.prodi }}
                                </th>

                                <td class="px-4 py-3 text-center">
                                    {{ item.angsuran1 }}
                                </td>

                                <td class="px-4 py-3 text-center">
                                    {{ item.angsuran2 }}
                                </td>

                                <td class="px-4 py-3 font-medium text-right font-semibold text-violet-600">
                                    {{ item.totalUKT }}
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>

            </div>
        </section>

        <Footer />
        <ScrollToTop />
        <Switcher />
    </div>
</template>

<script setup>
import { biayaUkt } from '@/data/biaya';
import VueTypewriterEffect from "vue-typewriter-effect";
import bg from '@/assets/images/bg/4.jpg'
import map from '@/assets/images/map.svg'
</script>
