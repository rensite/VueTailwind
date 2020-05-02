<template>
    <div class="mx-3 p-5 text-center">
        <img class="mx-auto rounded-full border-2 border-blue-400 mb-3" :src="member.picture.large" alt="" /> 
        <p class="text-md leading-none mb-2">{{member.name.title}} {{member.name.first}} {{member.name.last}}</p>
        <p class="text-sm leading-none">{{member.location.city}} {{member.location.state}}</p>
    </div>
</template>

<script>
    export default {
        name: "Member",
        props: {
            "member": Object
        }
    }
</script>