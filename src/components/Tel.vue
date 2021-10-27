<template>
    <p class="tel" :class="{ reversed: reversed }">
        <span class="icon"></span>03-1234-5678
    </p>
</template>

<script>
export default {
    props: {
        reversed: Boolean
    }
}
</script>

<style lang="scss" scoped>
    .tel {
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

        &.reversed {
            color: $bg-clr-sub;

            span {
                background: url('~assets/img/icon-phone-white.png') no-repeat;
                background-size: cover;
            }
        }
    }
</style>