<template>
    <p class="tel-number" :class="{ 'color-reversed': colorReversed }">
        <span class="icon"></span>03-6265-3710
    </p>
</template>

<script>
export default {
    props: {
        colorReversed: Boolean
    }
}
</script>

<style lang="scss" scoped>
    .tel-number {
        display: flex;
        align-items: center;

        letter-spacing: $ls-lg;
        color: $clr-main;
        font-size: 24px;
        font-weight: bold;

        span {
            --icon-size: 27px;

            width: var(--icon-size);
            height: var(--icon-size);
            background: url('~assets/img/icon-phone.png') no-repeat;
            background-size: cover;
            margin-right: 6px;
        }

        &.color-reversed {
            color: $bg-clr-sub;

            span {
                background: url('~assets/img/icon-phone-white.png') no-repeat;
                background-size: cover;
            }
        }
    }
</style>