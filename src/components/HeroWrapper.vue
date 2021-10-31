<template>
    <div class="hero-wrapper">
        <Hero v-for="object in objects" :key="object.id" :object="object" />
    </div>
</template>

<script>
export default {
    props: {
        objects: Array,
    }
}
</script>

<style lang="scss" scoped>
    .hero-wrapper {
        display: grid;
        justify-items: stretch;
        grid-template-columns: 1fr;

        @include mq(tab) {
            grid-template-columns: repeat(2, minmax(200px, 1fr));
        }
    }
</style>