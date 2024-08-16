<template>
  <footer class="flex flex-col items-center pt-16 gap-14">
    <header class="flex justify-around w-full">
      <aside class="flex list-none gap-3 font-medium">
        <div class="flex flex-col gap-3 text-[#2947A9]">
          <li>Dirección:</li>
          <li>Telefono:</li>
          <li>Email:</li>
        </div>
        <div class="flex flex-col gap-3">
          <li>658 Av Libertador, Buenos Aires</li>
          <li>+54 11022703</li>
          <li>hello@thebox.com</li>
        </div>
      </aside>
      <aside class="flex flex-col gap-5">
        <h3 class="flex items-center text-xl font-bold gap-2 text-[#2947A9]">
          <img src="/Random Symboles 3.png" alt="logo" />TheBox
        </h3>
        <div class="flex flex-col gap-2">
          <h4 class="font-medium text-[#2947A9]">Redes Sociales:</h4>
          <div class="flex gap-3">
            <a href="#">
              <img src="/facebook.png" alt="facebook" />
            </a>

            <a href="#">
              <img src="/linkedin.png" alt="linkedin" />
            </a>
            <a href="#">
              <img src="/twitter.png" alt="twitter" />
            </a>
          </div>
        </div>
      </aside>
    </header>
    <section class="bg-[#2947A9] w-full text-center p-4 text-white font-medium">
      <p>© 2024 TheBox. Todos los derechos reservados.</p>
    </section>
  </footer>
</template>

<script>
export default {}
</script>

<style scoped>
img {
  width: 40px;
  height: 40px;
}
</style>
