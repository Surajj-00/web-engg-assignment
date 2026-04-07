<script setup>
import { ArrowRight } from '@lucide/vue';
import Button from '../ui/Button.vue';


</script>

<template>
  <section class="container-main px-8 py-16 lg:px-36 lg:py-20 flex flex-col items-center justify-center gap-3 bg-primary-dark text-center">

    <h2 class="heading">Share Your Enterprise AI Vision</h2>
    <p class="text-xs md:text-sm pb-4 font-semibold text-center text-pretty">Align business needs with applicable Gen AI use cases.</p>

    <Button class="group">Schedule a Conversation
      <ArrowRight class="inline w-4 h-4 transition-transform group-hover:translate-x-1" />
    </Button>

  </section>
</template>
