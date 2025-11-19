<template>
  <div class="text-center py-6">
    <p class="mb-0 text-slate-400 text-sm">
      © {{ year }} PMB UMPKU Surakarta.
      <i class="mdi mdi-heart text-red-600"></i>
       PDSI.
    </p>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const year = ref(new Date().getFullYear())
</script>
