<template>
    <div>
        <Navbar/>

        <section class="relative pt-16 pb-12 md:pt-24 md:pb-16 lg:pt-32 lg:pb-24 bg-gray-50 dark:bg-slate-900">
            <div class="container relative">
                <div class="grid md:grid-cols-12 grid-cols-1 items-center gap-10 justify-center">
                    
                    <div class="lg:col-span-12 md:col-span-12 mx-auto text-center w-full max-w-4xl"> 
                        
                        <h5 class="mb-8 text-3xl md:text-2xl lg:text-3xl font-extrabold text-gray-900 dark:text-white leading-snug">
                            Brosur Penerimaan Mahasiswa Baru <br> <span class="text-violet-600">UMPKU Surakarta</span>
                        </h5>
                        
                        <div class="relative overflow-hidden rounded-2xl shadow-2xl shadow-violet-500/30 cursor-pointer group mb-6" @click="toggleZoom">
                            <img :src="productImg" alt="Visual Brosur Utama" class="w-full h-auto object-cover transition-all duration-500 group-hover:scale-[1.01]"/>
                            
                            <div class="absolute inset-0 bg-black/20 opacity-0 group-hover:opacity-100 transition-opacity flex items-center justify-center">
                                <i class="iconoir-zoom-in text-white text-4xl p-3 bg-white/30 rounded-full"></i>
                            </div>
                        </div>

                        <div class="flex justify-center mt-6">
                            <button type="button" @click="downloadBrosur"
                                    class="h-12 px-8 tracking-wide inline-flex items-center justify-center font-bold rounded-lg bg-violet-600 text-white shadow-lg shadow-violet-500/50 hover:bg-violet-700 transition duration-300 transform hover:scale-[1.02] text-base">
                                <i class="iconoir-download me-2"></i> Unduh Brosur PMB UMPKU
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <div class="relative">
            <div class="shape overflow-hidden z-1 text-white dark:text-slate-900">
                <svg viewBox="0 0 2880 48" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M0 48H1437.5H2880V0H2160C1442.5 52 720 0 720 0H0V48Z" fill="currentColor"></path>
                </svg>
            </div>
        </div>

        <Footer/>
        <ScrollToTop/>
        <Switcher/>

        <div v-if="isZoomed" @click.self="toggleZoom" 
             class="fixed inset-0 z-[9999] bg-black/95 flex items-center justify-center p-4 transition-opacity duration-300 overflow-auto"> 
            
            <button @click="toggleZoom" class="fixed top-6 right-6 text-white text-3xl z-[10000] p-2 rounded-full bg-black/50 hover:bg-black/80 transition">
                &times;
            </button>

            <img :src="productImg" alt="Brosur Zoom" class="w-auto h-auto max-w-full max-h-none shadow-2xl rounded-lg mx-auto my-auto cursor-default"/>
            
        </div>
    </div>
</template>

<script setup>
    import { ref, watch } from 'vue';
    import productImg from '@/assets/images/brosur/brosur-1.jpeg'; 

    // --- LOGIKA ZOOM GAMBAR ---
    const isZoomed = ref(false);

    const toggleZoom = () => {
        isZoomed.value = !isZoomed.value;
    };
    
    // Mengontrol scrolling body saat modal terbuka
    watch(isZoomed, (newValue) => {
        document.body.style.overflow = newValue ? 'hidden' : '';
    });


    // --- LOGIKA DOWNLOAD GAMBAR ---
    const downloadBrosur = () => {
        const link = document.createElement('a');
        
        link.href = productImg; 
        link.download = 'brosur_pmb_umpku.jpeg'; 
        
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
    };
</script>