<script setup>
import { ChevronDown, Menu, X } from '@lucide/vue';
import { onUnmounted, ref } from 'vue';
import Button from '../ui/Button.vue';

const navLinks = [
  {
    name: 'Services',
    path: '/services',
    dropdown: [
      { label: 'Big Data Analytics', path: '#' },
      { label: 'Big Data Consulting', path: '#' },
      { label: 'AI Development', path: '#' },
      { label: 'Software Development', path: '#' },
    ]
  },
  {
    name: 'Industries',
    path: '/industries',
    dropdown: [
      { label: 'Healthcare', path: '#' },
      { label: 'Automobile', path: '#' },
      { label: 'HR Tech', path: '#' },
      { label: 'Printing', path: '#' },
    ]
  },
  { name: 'Why Radixweb', path: '/why-radixweb' },
  { name: 'Work', path: '/work' },
  { name: 'About', path: '/about' },
  { name: 'Insights', path: '/insights' },
];

const isMenuOpen = ref(false);
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  document.body.style.overflow = isMenuOpen.value ? 'hidden' : '';
};

const activeMobileDropdown = ref(null);

const toggleMobileDropdown = (name) => {
  activeMobileDropdown.value = activeMobileDropdown.value === name ? null : name;
};

onUnmounted(() => {
  document.body.style.overflow = '';
});

</script>

<template>
  <div class="container-main">
    <header
      class="container-main flex items-center justify-between lg:justify-around p-4 md:p-6 lg:p-3 fixed top-0 left-0 right-0 z-50 bg-white shadow-md">
      <img width="45" src="@/assets/images/logo.svg" alt="logo" />

      <nav class="hidden lg:flex items-center justify-between gap-8">

        <div v-for="link in navLinks" :key="link.name" class="group relative">

          <!-- nav link -->
          <RouterLink :to="link.path" class="text-sm font-medium flex items-center gap-1 ">
            {{ link.name }}
            <ChevronDown v-if="link.dropdown" class="w-3 h-3 transition-transform duration-300 group-hover:rotate-180" />
          </RouterLink>

          <!-- dropdown — only if link has dropdown -->
          <div v-if="link.dropdown" class="hidden group-hover:block absolute top-full left-0
             bg-white shadow-lg rounded-lg py-3 min-w-48 z-50
             border border-gray-100">
            <RouterLink v-for="item in link.dropdown" :key="item.label" :to="item.path"
              class="block px-4 py-2 text-xs hover:bg-green-50 hover:text-btn-primary transition-colors">
              {{ item.label }}
            </RouterLink>
          </div>

        </div>

      </nav>

      <button type="button"
        class="bg-btn-primary text-sm py-1.5 px-10 rounded-md text-white cursor-pointer hidden lg:block">
        Let's Talk
      </button>

      <button @click="toggleMenu" class="lg:hidden">
        <Menu v-if="!isMenuOpen" />
        <X v-if="isMenuOpen" />
      </button>
    </header>

    <!-- overlay -->
    <div v-show="isMenuOpen" @click="toggleMenu" class="fixed inset-0 bg-black/50 z-50 lg:hidden" />

    <!-- side drawer menu-->
    <div
      class="fixed top-0 right-0 h-full w-72 bg-white z-50 lg:hidden transform transition-transform duration-300 ease-in-out flex flex-col p-8 gap-5"
      :class="isMenuOpen ? 'translate-x-0' : 'translate-x-full'">
      <!-- close button -->
      <button @click="toggleMenu" class="self-end">
        <X class="w-6 h-6" />
      </button>

      <!-- links -->
      <div v-for="link in navLinks" :key="link.name" class="flex flex-col">

        <!-- link row -->
        <div class="flex items-center justify-between"
          @click="link.dropdown ? toggleMobileDropdown(link.name) : toggleMenu()">
          <RouterLink :to="link.path" class="text-sm md:text-base">
            {{ link.name }}
          </RouterLink>
          <ChevronDown v-if="link.dropdown" class="w-4 h-4 transition-transform duration-300"
            :class="activeMobileDropdown === link.name ? 'rotate-180' : ''" />
        </div>

        <!-- mobile dropdown -->
        <div v-show="activeMobileDropdown === link.name"
          class="flex flex-col pl-4 mt-2 gap-1 border-l-2 border-btn-primary">
          <RouterLink v-for="item in link.dropdown" :key="item.label" :to="item.path" @click="toggleMenu"
            class="text-xs text-gray-500 active:bg-green-50 active:text-btn-primary transition-colors py-1">
            {{ item.label }}
          </RouterLink>
        </div>

      </div>

      <!-- button -->
      <button class="bg-btn-primary text-white px-5 py-2 rounded-md text-sm md:text-base">Let's Talk</button>
    </div>
  </div>
</template>
