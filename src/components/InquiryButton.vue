<template>
    <div class="btn-inquiry" :class="{ reversed: reversed }">
        <a href="/inquiry">
            <span class="icon"></span>
            <span>
                <slot>お問い合わせ</slot>
            </span>
        </a>
    </div>
</template>

<script>
    export default {
        props: {
            reversed: Boolean
        }
    }
</script>

<style lang="scss" scoped>
    .btn-inquiry {
        transition: $trans-in;
        background-color: $clr-main;
        color: $bg-clr-sub;
        line-height: $lh-200;
        display: inline-block;
        padding: 14px 10px;

        &.reversed {
            background-color: $bg-clr-sub;
            color: $clr-main;

            .icon {
                background-image: url('~assets/img/icon-mail.png');
            }
        }

        a {
            display: flex;
            align-items: center;

            span {
                --icon-size: 28px;
                font-weight: 500;

                &.icon {
                    height: var(--icon-size);
                    width: var(--icon-size);
                    background-size: cover;
                    background-image: url('~assets/img/icon-mail-white.png');
                    margin-right: 6px;
                }
            }
        }
    }
</style>