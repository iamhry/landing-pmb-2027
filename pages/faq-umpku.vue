<template>
    <div>

        <Navbar />
<section class="relative md:py-24 py-16">
            <div class="container relative lg:mt-18 mt-16">
                <div class="grid grid-cols-1 pb-6 text-center">
                    <span class="text-violet-600 font-semibold mb-3 uppercase">Faq's</span>
                    <h4 class="mb-6 md:text-3xl text-2xl md:leading-normal leading-normal font-semibold">Frequently Asked Questions.</h4>
                    <p class="text-slate-400 max-w-xl mx-auto">Temukan jawaban cepat untuk pertanyaan umum seputar pendaftaran, biaya, dan program studi kami. Kami merangkum semua yang Anda butuhkan di sini.</p>
                </div>
                <div class="grid md:grid-cols-12 grid-cols-1 items-center gap-6">
                    <FaqUmpku />
                    <div class="lg:col-span-6 md:col-span-5">
                        <SyaratFaq />
                    </div>
                </div>
            </div>  
        </section>

        <Footer/>

        <Switcher/>

        <ScrollToTop/>
    </div>
</template>

<script setup>

    import bg from '@/assets/images/bg/3.jpg'

    const sections = ref([
        { id: "tech", name: "Buying Questions" },
        { id: "general", name: "General Questions" },
        { id: "payment", name: "Payments Questions" },
        { id: "support", name: "Support Questions" },
    ])

    const activeSection = ref(null)

    onMounted(() => {
        const options = {
            root: null, 
            rootMargin: "0px",
            threshold: 0.5,
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
            if (entry.isIntersecting) {
                activeSection.value = entry.target.id;
            }
            });
        }, options);

        sections.value.forEach((section) => {
            const element = document.getElementById(section.id);
            if (element) observer.observe(element);
        });
    });

</script>
