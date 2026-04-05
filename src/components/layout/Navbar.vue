<script setup>
import { ChevronDown, Menu, X } from '@lucide/vue'
import { ref } from 'vue'
import Button from '../ui/Button.vue'

const navLinks = [
  { name: 'Services', path: '/services' },
  { name: 'Industries', path: '/industries' },
  { name: 'Why Radixweb', path: '/why-radixweb' },
  { name: 'Work', path: '/work' },
  { name: 'About', path: '/about' },
  { name: 'Insights', path: '/insights' },
]

const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <div class="">
    <header class="flex items-center justify-between lg:justify-around p-4">
      <img src="@/assets/images/logo.svg" alt="logo" />

      <nav class="hidden lg:flex items-center justify-between gap-8">
        <RouterLink v-for="link in navLinks" :key="link.name" :to="link.path" class="text-sm">
          {{ link.name }}
          <ChevronDown class="w-3 h-3 inline" />
        </RouterLink>
      </nav>

      <button
        type="button"
        class="bg-btn-primary text-sm py-1.5 px-10 rounded-md text-white cursor-pointer hidden lg:block"
      >
        Let's Talk
      </button>

      <button @click="toggleMenu" class="lg:hidden">
        <Menu v-if="!isMenuOpen" />
        <X v-if="isMenuOpen" />
      </button>
    </header>

    <!-- overlay -->
    <div v-show="isMenuOpen" @click="toggleMenu" class="fixed inset-0 bg-black/50 z-40 lg:hidden" />

    <!-- slide drawer -->
    <div
      class="fixed top-0 right-0 h-full w-72 bg-white z-50 lg:hidden transform transition-transform duration-300 ease-in-out flex flex-col p-8 gap-6"
      :class="isMenuOpen ? 'translate-x-0' : 'translate-x-full'"
    >
      <!-- close button -->
      <button @click="toggleMenu" class="self-end">
        <X class="w-6 h-6" />
      </button>

      <!-- links -->
      <RouterLink v-for="link in navLinks" :key="link.name" :to="link.path" @click="toggleMenu">
        {{ link.name }}
        <ChevronDown class="w-3 h-3 inline" />
      </RouterLink>

      <!-- button -->
      <button class="bg-btn-primary text-white px-5 py-2 rounded-md">Let's Talk</button>
    </div>
  </div>
</template>
