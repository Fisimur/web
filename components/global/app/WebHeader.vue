<template>
  <div class="flex justify-between items-center">
    <nuxt-link :to="{ name: 'index' }">
      <div class="inline-flex items-center">
        <img src="/logo1-100x90.png" alt="Logo de Fisimur" />
        <h1
            class="text-2xl font-semibold leading-6 transition ease-in-out duration-300 hover:bg-blue-100 py-2 pl-1 pr-5 inline-block"
        >
          Fisimur.org
        </h1>
      </div>
    </nuxt-link>
    <div>
      <h2 class="text-xl text-gray-700 pl-1">La física está ahí fuera</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: 'WebHeader',
}
</script>
