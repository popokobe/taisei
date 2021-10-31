<template>
    <div class="title">
        <span>{{ title.sub }}</span>
        <h2>{{ title.main }}</h2>
    </div>
</template>

<script>
export default {
    props: {
        title: Object
    }
}
</script>

<style lang="scss" scoped>
.title {
    text-align: left;
    font-weight: 500;
    letter-spacing: $ls-lg;
    position: relative;

    &::before {
        content: "";
        position: absolute;
        display: block;
        background: rgba($clr-main, 0.4);
        top: -20%;
        left: -2%;
        --diameter: 40px;
        width: var(--diameter);
        height: var(--diameter);
        border-radius: 50%;

        @include mq(tab) {
            --diameter: 50px;
        }
    }

    span {
        color: $clr-main;
    }

    h2 {
        font-size: 2.4rem;

        @include mq(tab) {
            font-size: 3.2rem;
        }
    }
}
</style>