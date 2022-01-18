<template>
  <div class="h-full">
    <header class="h-40 py-6 px-8 flex items-center justify-between bg-gray-200">
      <S2Logo/>
      <S2Navigation/>
    </header>
    <main class="h-custom py-6 px-8">
      <Nuxt />
    </main>
  </div>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>

<style scoped>
.h-custom {
  height: calc(100vh - 10rem);
}
</style>