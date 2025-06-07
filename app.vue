<script setup lang="ts">
const nuxtApp = useNuxtApp();
const loading = ref(true);
const showIntro = ref(true);

nuxtApp.hook("page:start", () => {
  loading.value = true;
});

nuxtApp.hook("page:finish", () => {
  loading.value = false;
  setTimeout(() => {
    showIntro.value = false;
  }, 3000);
});
</script>
<template>
  <div>
    <Transition
      enter-active-class="transition-all duration-500 ease-out"
      leave-active-class="transition-all duration-500 ease-in"
      enter-from-class="opacity-0 scale-95"
      enter-to-class="opacity-100 scale-100"
      leave-from-class="opacity-100 scale-100"
      leave-to-class="opacity-0 scale-75 duration-1000 ease-in-out skew-y-16"
    >
      <LoadingIntro v-if="showIntro" />
    </Transition>
    <NuxtLayout>
      <UApp>
        <NuxtPage />
      </UApp>
    </NuxtLayout>
    <NuxtLoadingIndicator />
  </div>
</template>
