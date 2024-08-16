<template>
  <div>
    <div class="mb-4">
      <input
        type="text"
        v-model="searchTerm"
        placeholder="Buscar por nombre"
        class="px-4 py-2 border border-gray-300 rounded-lg w-full" />
    </div>
    <table
      v-if="filteredProjects.length"
      class="min-w-full bg-white border border-gray-200">
      <thead>
        <tr>
          <th
            class="px-6 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
            Imagen
          </th>
          <th
            class="px-6 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
            Nombre
          </th>
          <th
            class="px-6 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
            Categoría
          </th>
          <th
            class="px-6 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
            Editar
          </th>
          <th
            class="px-6 py-3 border-b-2 border-gray-200 bg-gray-100 text-left text-xs font-semibold text-gray-600 uppercase tracking-wider">
            Borrar
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="project in filteredProjects"
          :key="project.id"
          class="hover:bg-gray-100">
          <td class="px-6 py-0 border-b border-gray-200">
            <img
              :src="project.img"
              alt="Imagen del proyecto"
              class="w-20 rounded-lg h-auto" />
          </td>
          <td class="px-6 py-4 border-b border-gray-200">{{ project.name }}</td>
          <td class="px-6 py-4 border-b border-gray-200">
            {{ project.category }}
          </td>
          <td class="px-6 py-4 border-b border-gray-200">
            <button
              @click="editProject(project.id)"
              class="text-blue-600 hover:text-blue-900">
              Editar
            </button>
          </td>
          <td class="px-6 py-4 border-b border-gray-200">
            <button
              @click="deleteProject(project.id)"
              class="text-red-600 hover:text-red-900">
              Borrar
            </button>
          </td>
        </tr>
      </tbody>
    </table>
    <div v-else class="text-center py-4 text-gray-600">
      No hay posts disponibles.
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      searchTerm: '',
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
    }
  },
  computed: {
    filteredProjects() {
      return this.projects.filter(project =>
        project.name.toLowerCase().includes(this.searchTerm.toLowerCase())
      )
    },
  },
  methods: {
    editProject(id) {
      // Lógica para editar el proyecto
      console.log(`Editar proyecto con id: ${id}`)
    },
    deleteProject(id) {
      // Lógica para borrar el proyecto
      this.projects = this.projects.filter(project => project.id !== id)
    },
  },
}
</script>
