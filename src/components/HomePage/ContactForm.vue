<template>
  <section
    class="flex flex-col items-center justify-center w-full gap-8 bg-[#F6F8F7] py-16"
    id="contact">
    <div class="flex flex-col items-center justify-center text-center gap-3">
      <h2 class="font-black text-4xl">¿Qué podemos hacer por usted?</h2>
      <p class="max-w-md text-gray-800 max-md:px-8 text-balance">
        Estamos listos para trabajar en un proyecto de cualquier complejidad, ya
        sea comercial o residencial.
      </p>
    </div>

    <form
      @submit.prevent="handleSubmit"
      class="flex flex-col items-center justify-center max-md:w-full max-md:px-6 gap-y-5">
      <div
        class="grid grid-cols-1 md:grid-cols-2 gap-x-10 gap-y-5 max-md:w-full">
        <div class="flex flex-col gap-1 w-full">
          <label for="name" class="text-xs font-medium"
            >Nombre <span class="text-red-600">*</span></label
          >
          <input
            type="text"
            id="name"
            v-model="form.name"
            class="rounded-lg bg-white placeholder:px-3 px-3 h-8 w-full"
            required />
        </div>
        <div class="flex flex-col gap-1">
          <label for="email" class="text-xs font-medium"
            >Email <span class="text-red-600">*</span></label
          >
          <input
            type="email"
            id="email"
            v-model="form.email"
            class="rounded-lg bg-white placeholder:px-3 px-3 w-full h-8"
            required />
        </div>
        <div class="flex flex-col gap-1">
          <label for="reason" class="text-xs font-medium"
            >Razon del mensaje</label
          >
          <select
            id="reason"
            class="rounded-lg bg-white px-2 h-8 text-sm w-full"
            v-model="form.reason">
            >
            <option value="question">Consultas</option>
            <option value="budget">Presupuesto</option>
            <option value="partnership">Socios</option>
            <option value="other">Otro</option>
          </select>
        </div>
        <div class="flex flex-col gap-1">
          <label for="phone" class="text-xs font-medium">Teléfono</label>
          <input
            type="tel"
            id="phone"
            v-model="form.phone"
            class="rounded-lg bg-white placeholder:px-3 px-3 w-full h-8" />
        </div>
      </div>
      <div class="flex w-full flex-col gap-1">
        <label for="message" class="text-xs font-medium"
          >Mensaje <span class="text-red-600">*</span></label
        >
        <textarea
          id="message"
          required
          v-model="form.message"
          class="w-full px-3 rounded-lg py-2 min-h-24"></textarea>
      </div>
      <button
        class="px-12 py-2 w-full rounded-lg bg-[#2947A9] text-white"
        type="submit">
        Enviar
      </button>
    </form>
  </section>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: '',
        reason: 'question',
        phone: '',
      },
    }
  },
  methods: {
    handleSubmit() {
      alert('Formulario enviado')
      this.form.name = ''
      this.form.email = ''
      this.form.message = ''
      this.form.reason = 'question'
      this.form.phone = ''

      // Resetear otros campos del formulario
    },
  },
}
</script>
