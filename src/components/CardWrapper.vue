<template>
    <div class="card-wrapper">
        <Card v-for="object in objects" :key="object.id" :object="object"  />
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
    .card-wrapper {
        display: grid;
        justify-items: stretch;
        grid-template-columns: 1fr;
        gap: 20px;

        @include mq(tab) {
            grid-template-columns: repeat(2, minmax(300px, 1fr));
        }
    }
</style>