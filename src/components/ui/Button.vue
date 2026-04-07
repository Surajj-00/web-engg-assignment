<script setup>
defineProps({
  extraClass: { type: String, default: '' }
});
</script>

<template>
  <button
    class="bg-btn-primary text-white text-xs md:text-sm px-6 py-2 rounded-sm flex items-center gap-2 cursor-pointer active:scale-95 transition-transform duration-150">
    <slot/>
  </button>
</template>
