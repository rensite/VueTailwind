<template>
  <div>
    <Hero title="Vue.js x Tailwind.css"/>
    <Team :team="team"/>
    <Gallery :pictures="pictures" @morePictures="morePictures" />
  </div>
</template>

<script>
  import Hero from '@/components/Hero.vue'
  import Team from '@/components/Team.vue'
  import Gallery from '@/components/Gallery.vue'
  import axios from 'axios'

  export default {
    name: 'Home',
    components: {
      Hero,
      Team,
      Gallery
    },
    data () {
      return {
        team: [],
        pictures: []
      }
    },
    created () {
      this.getTeamMemebers()
    },
    methods: {
      getTeamMemebers () {
        axios
          .get('https://randomuser.me/api/?nat=us&results=6')
            .then(response => (this.team = response.data.results))
            .error(error => (console.log(error)))
      },

      morePictures (page = 1) {
        axios
          .get(`https://picsum.photos/v2/list?page=${page}&limit=4`)
            .then(response => (this.pictures = this.pictures.concat(response.data)))
            .error(error => (console.log(error)))
      }
    }
  }
</script>
