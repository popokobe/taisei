<template>
    <ul class="sns">
        <SocialIcon v-for="icon in sns" :key=icon.id :icon=icon />
    </ul>
</template>

<script>
export default {
    props: {
        sns: Array
    }
}
</script>

<style lang="scss" scoped>
    .sns {
        display: flex;
    }
</style>