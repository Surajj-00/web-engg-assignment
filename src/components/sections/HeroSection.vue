<script setup>
import { ArrowRight } from '@lucide/vue';
import Button from '../ui/Button.vue';
</script>

<template>
  <div class="w-full h-auto px-4 py-16 md:py-24 bg-linear-to-br from-green-100 to-green-200">
    <div class="flex flex-col items-center justify-center text-center gap-4 lg:px-28 md:gap-6">

      <span class="font-bold text-xs md:text-base lg:text-lg">Big Data and Gen AI Services </span>

      <h1 class="font-medium text-xl leading-6 md:text-3xl md:leading-8 lg:text-5xl lg:leading-14 text-pretty">
        Extract and Process PB Scale Data for Predictive Insights and Threat Assessments
      </h1>

      <p class="md:w-2/3 text-xs text-pretty lg:text-base">
        Take complexity out of business data for actionable insights. Help mature business processes
        harness the benefits of AI-led personalization and scalable intelligence.
      </p>

      <Button class="group">
        Prepare Data for AI
        <ArrowRight class="inline w-4 h-4 transition-transform group-hover:translate-x-1" />
      </Button>
    </div>
  </div>
</template>
