<template>
  <section class="text-center bg-blue-300">
    <div class="mx-auto w-full md:w-1/2 h-full flex flex-col items-center justify-center py-20 md:py-20 lg:py-40 px-5 md:px-0">
      <h1 class="text-3xl md:text-5xl text-white leading-none mb-3">{{title}}</h1>
      <p class=" text-white mb-6">Responsive demo page. Technologies: Vue, Tailwind, axios. Source code is available at <a href="https://github.com/rensite/VueTailwind" target="_blank">GitHub.com</a>.</p>
      <button class="btn mb-3">Read More</button>
      <p class="text-sm text-white opacity-50">The button does nothing ;)</p>
    </div>
  </section>
</template>

<script>
  export default {
    name: 'Hero',
    props: {
      title: String
    }
  }
</script>

<style lang="scss" scoped>
  .btn {
    @apply px-5 py-2 text-white rounded-lg border-2 border-white ; 

    &:hover {
      @apply px-5 py-2 text-blue-500 rounded-lg border-2 border-white bg-white; 
    }

    &:focus {
        @apply outline-none; 
    }
  }
</style>