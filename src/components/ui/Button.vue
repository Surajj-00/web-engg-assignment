<script setup>
defineProps({
  extraClass: { type: String, default: '' }
});
</script>

<template>
  <button
    class="bg-btn-primary text-white text-xs md:text-sm px-6 py-3 rounded-md flex items-center gap-2 cursor-pointer">
    <slot />
  </button>
</template>
