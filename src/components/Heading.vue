<template>
    <div class="title" :class="{ 'color-reversed' : colorReversed }">
        <span>{{ title.sub }}</span>
        <h2>{{ title.main }}</h2>
    </div>
</template>

<script>
export default {
    props: {
        title: Object,
        colorReversed: Boolean
    }
}
</script>

<style lang="scss" scoped>
.title {
    width: clamp(250px ,70vw ,480px );
    text-align: left;
    font-weight: 500;
    letter-spacing: $ls-lg;
    position: relative;

    &::before {
        content: "";
        position: absolute;
        display: block;
        background: rgba($clr-main, 0.4);
        top: -8px;
        left: -12px;
        --diameter: 40px;
        width: var(--diameter);
        height: var(--diameter);
        border-radius: 50%;

        @include mq(tab) {
            --diameter: 50px;
            top: -14px;
            left: -17px;
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

    &.color-reversed {
        &::before {
            background: rgba($bg-clr-sub, 0.4);
        }

        span,
        h2
         {
            color: $bg-clr-sub;
        }
    }
}
</style>