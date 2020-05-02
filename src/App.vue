<template>
  <div id="app">
    <header class="w-full">
      <div class="container mx-auto py-3 px-4 flex items-center justify-between">
        <img class="h-10 w-auto" src="@/assets/logo.svg" alt="logo" />
        <HeaderNav :navLinks="navLinks" />
      </div>
    </header>

    <router-view/>

    <footer class="text-center text-sm text-gray-400 mb-4" >&copy; 2020 Vue, Tailwind.css</footer>
  </div>
</template>

<script>
import HeaderNav from "@/components/HeaderNav"

export default {
  name: 'app',
  components: {
    HeaderNav
  },
  data () {
    return {
      navLinks: [
        {"caption": "Home", "href": "/"},
        {"caption": "Team", "href": "#team"},
        {"caption": "Gallery", "href": "#gallery"},
      ]
    }
  }
}
</script>
