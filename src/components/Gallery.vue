<template>
    <div class="container mx-auto text-center pb-20 px-5" id="gallery">
        <h2 class="text-center leading-none text-4xl mb-2">Gallery</h2>
        <p class="text-gray-600 mb-8">Parent component fetches the API on button click in child component</p>

        <div v-if="!isEmpty" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 lg:grid-cols-4 gap-3 mb-10">
            <img class="h-64 sm:h-32 lg:h-48 w-full object-cover" v-for="picture in pictures" :key="picture.id" :src="picture.download_url" />
        </div>

        <img v-else class="mx-auto  mb-10" src="@/assets/loading.svg" />

        <button @click="morePictures" class="btn">Load More</button>
    </div>
</template>

<script>
    export default {
        name: "Gallery",
        props: {
            pictures: {
                type: Array,
                default: () => {
                    return []
                }
            }
        },
        data () {
            return {
                page: 2
            }
        },
        computed: {
            isEmpty () {
                return (Object.keys(this.pictures).length === 0)
            }
        },
        created() {
            this.$emit('morePictures')
        },
        methods: {
            morePictures () {
                this.$emit('morePictures', this.page++)
            }
        }
    }
</script>

<style lang="scss" scoped>
  .btn {
    @apply px-5 py-2 text-blue-500 rounded-lg border-2 border-blue-500; 

    &:hover {
      @apply px-5 py-2 text-white rounded-lg border-2 border-blue-500 bg-blue-500; 
    }

    &:focus {
        @apply outline-none; 
    }
  }
</style>