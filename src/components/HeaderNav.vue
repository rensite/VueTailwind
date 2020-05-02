<template>
    <div class="flex">
        <a v-for="link in navLinks" class="ml-4" :href="link.href" :key="link.href">{{link.caption}}</a>
    </div>
</template>

<script>
    export default {
        name: 'HeaderNav',
        props: {
            navLinks: Array
        }
    }
</script>