<template>
  <section
    class="bg-[#F6F8F7] py-24 flex flex-col items-center gap-10 w-full max-xl:px-6">
    <h2 class="font-bold text-3xl">Servicios</h2>
    <div
      class="grid grid-cols-1 gap-8 md:gap-24 md:grid-cols-3 w-full max-w-6xl">
      <div
        v-for="(item, index) in data"
        :key="item.title"
        :class="[
          'flex flex-col items-center  border py-8 p-4 h-full justify-between rounded-md shadow-lg gap-3 max-md:',
          index % 2 !== 0 ? 'bg-[#2947A9] text-white' : 'bg-white',
        ]">
        <img :src="item.icon" alt="icon" class="w-8 object-contain" />
        <span class="border-b-2 mt-2 w-1/2" />
        <h3 class="text-xl font-semibold">{{ item.title }}</h3>
        <p class="text-center max-w-48 text-gray-800">{{ item.description }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  setup() {
    return {
      data: [
        {
          icon: '/icon.png',
          title: 'Construcción',
        },
        {
          icon: '/icon (1).png',
          title: 'Renovación',
        },
        {
          icon: '/icon (2).png',
          title: 'Consultas',
        },
        {
          icon: '/icon (3).png',
          title: 'Servicios de reparación',
        },
        {
          icon: '/icon (4).png',
          title: 'Arquitectura',
        },
        {
          icon: '/icon (5).png',
          title: 'Electricidad',
        },
      ],
    }
  },
}
</script>
