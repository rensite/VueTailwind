<template>
    <div class="container mx-auto py-16 md:py-20" id="team">
        <h2 class="text-center leading-none text-4xl mb-2" >Team</h2>
        <p class="text-gray-600 text-center mb-4 md:mb-10">The data is fetched with axios from randomuser.me</p>
        <div v-if="team.length" class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-4 xl:grid-cols-6">
            <Member v-for="member in team" :key="member.login.uuid" :member="member" />
        </div>
        <div v-else class="flex align-center justify-center">
            <img src="@/assets/loading.svg" />
        </div>
    </div>
</template>

<script>
    import Member from "@/components/Member.vue"

    export default {
        name: "Team",
        props: {
            "team": {
                type: Array,
                default: () => {
                    return []
                }
            }
        },
        components: {
            Member
        }
    }
</script>