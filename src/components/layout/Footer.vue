<script setup>
import { ChevronRight } from '@lucide/vue';

const footerLinks = [
  {
    heading: 'Industry',
    links: ['Automobile', 'HR Tech', 'Healthcare', 'Printing']
  },
  {
    heading: 'Pages',
    links: ['Services', 'Blogs', 'News', 'Videos']
  },
  {
    heading: 'Services',
    links: ['Ai Development', 'Software Development', 'Embedded System', 'Custom Software Development']
  }
];
</script>

<template>
  <footer class="bg-footer-bg text-white">
    <div class="md:flex items-center justify-between gap-4 px-12 md:px-28 py-12">

      <div class="md:w-4/12 pb-4">
        <h2 class="font-medium text-base md:text-lg lg:text-xl pb-2 md:pb-4">Stay Connected</h2>
        <p class="text-xs md:text-sm">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Illum quae, culpa repudiandae ratione perferendis expedita placeat dolorum. Aliquam odio cum maiores voluptatem quos quae consequuntur magnam quod eaque soluta.</p>
      </div>

      <div class="md:grid grid-cols-3">
        <div v-for="col in footerLinks" :key="col.heading">
          <h4 class="font-medium text-base md:text-lg lg:text-xl pt-4 pb-2 md:pb-4">{{ col.heading }}</h4>
          <ul>
            <li v-for="link in col.links" :key="link" class="text-sm pb-2 md:pb-4 cursor-pointer">
              <ChevronRight class="inline w-3 h-3 text-black" />
              {{ link }}
            </li>
          </ul>
        </div>
      </div>


    </div>

    <!-- Copyright -->
    <div class="text-xs md:text-sm text-center py-4 border-t border-white/20 bg-white text-black">
      Copyright Reserved
    </div>
  </footer>
</template>
