<template>
    <div class="content-wrapper">
        <slot />
    </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
.content-wrapper {
    width: clamp(280px, 90vw, 1280px);
    margin: 0 auto;
}
</style>