<template>
  <section
    class="flex max-xl:flex-col gap-9 w-full md:px-44 py-24 justify-between max-xl:items-center items-start min-h-[800px]"
    id="projects ">
    <div class="flex flex-col max-md:items-center">
      <h2 class="font-noto font-bold flex text-4xl text-primary">Proyectos</h2>
      <aside
        class="flex flex-col max-md:w-10/12 max-xl:flex-row max-lg:gap-4 xl:gap-4 max-md:flex-wrap gap-10 justify-center py-5">
        <span
          :class="
            selectedCategory === null
              ? 'text-[#2947A9] border-l-4 pl-2 border-[#2947A9] font-semibold'
              : 'text-blue-800/50'
          "
          @click="filterByCategory(null)"
          class="cursor-pointer"
          >Todos</span
        >
        <div
          v-for="category in categories"
          :key="category"
          :class="
            selectedCategory === category
              ? 'text-[#2947A9] border-l-4 pl-2 border-[#2947A9] font-semibold'
              : 'text-blue-800/50'
          "
          @click="filterByCategory(category)"
          class="flex cursor-pointer">
          <span>
            {{ category }}
          </span>
        </div>
      </aside>
    </div>

    <article
      class="grid grid-cols-1 md:grid-cols-2 w-fit gap-8 place-items-center items-center">
      <div
        v-for="project in filteredprojects"
        :key="project.id"
        class="flex flex-col lg:w-[300px] h-72 min-h-64 max-md:w-full">
        <img :src="project.img" :alt="project.name" class="object-cover h-44" />
        <div
          class="w-auto bg-[#2947A9] text-white grow justify-between h-full flex flex-col p-2">
          <h3
            class="text-accent text-xl tracking-tight font-medium cursor-pointer text-gray-200">
            {{ project.name }}
          </h3>
          <p class="text-sm">{{ project.description }}</p>
        </div>
      </div>
    </article>
  </section>
</template>

<script>
export default {
  name: 'projectsList',
  data() {
    return {
      projects: [
        {
          id: 1,
          name: 'Hotel de infraestructura Wildstone',
          category: 'Commercial',
          description: '2715 Rivadavia, Buenos Aires',
          img: '/unsplash_T0iFfJw-rB0.png',
        },
        {
          id: 2,
          name: 'Edificio de piedra de los deseos',
          category: 'Comercial',
          description: '948 Av. Corrientes, Buenos Aires',
          img: '/unsplash_8oRCwrBn_Fc.png',
        },
        {
          id: 3,
          name: 'La casa del señor Parkinston',
          category: 'Residencia',
          description: '5813 Av. Avellaneda, Buenos Aires',
          img: '/unsplash_UV81E0oXXWQ.png',
        },
        {
          id: 4,
          name: 'Oregano Height',
          category: 'Otro',
          description: '257 Belgrano, Buenos Aires',
          img: '/unsplash_gMes5dNykus.png',
        },
      ],
      categories: [],
      selectedCategory: null,
    }
  },
  computed: {
    filteredprojects() {
      if (this.selectedCategory) {
        return this.projects.filter(
          project => project.category === this.selectedCategory
        )
      }
      return this.projects
    },
  },
  methods: {
    filterByCategory(category) {
      this.selectedCategory = category
    },
  },
  created() {
    // Extraer categorías únicas de los projectos
    this.categories = [
      ...new Set(this.projects.map(project => project.category)),
    ]
  },
}
</script>
