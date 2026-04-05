<script setup>
const stats = ['25+', '3000+', '30+', '97%'];
</script>

<template>
  <section class="px-8 py-16 lg:px-36 lg:py-20 flex flex-col items-center justify-center gap-6 bg-primary">

    <h2 class="heading">Experience You Can Trust</h2>
    <p class="text-xs md:text-sm text-center text-pretty">Helping you forecast evolving market needs with Big Data services.</p>

    <div class="flex flex-row items-center justify-center gap-8 md:gap-12 flex-wrap">
      <span v-for="stat in stats" :key="stat" class="text-[#02542D] text-2xl md:text-3xl font-normal font-stats">
        {{ stat }}
      </span>
    </div>
  </section>
</template>
