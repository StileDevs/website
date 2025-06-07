<script setup lang="ts">
import { motion } from "motion-v";
</script>

<template>
  <div class="fixed left-0 top-0 w-full h-full z-50 bg-[var(--ui-bg-muted)]">
    <div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2">
      <motion.div
        class="transition-all scale-50 flex items-center"
        :initial="{
          scale: 2.3,
          x: 800
        }"
        :animate="{
          scale: 1,
          x: 0
        }"
        :transition="{ type: 'easeInOut', duration: 0.6 }"
      >
        <AStileText class="scale-75" style="view-transition-name: astile-text" />
        <AStileLogo class="scale-75" style="view-transition-name: astile-logo" />
      </motion.div>
    </div>
  </div>
</template>
