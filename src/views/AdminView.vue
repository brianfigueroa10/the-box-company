<template>
  <section class="flex flex-col p-8 gap-5 min-h-[400px]">
    <div class="flex w-full justify-between">
      <h1 class="text-4xl font-bold">Dashboard</h1>
      <router-link
        to="/create-post"
        class="px-6 py-3 bg-green-700 text-white rounded-md hover:bg-green-900 transition-all"
        >Crear Post</router-link
      >
    </div>
    <TablePost />
  </section>
</template>

<script setup>
import TablePost from '/src/components/AdminPage/TablePost.vue'
</script>
