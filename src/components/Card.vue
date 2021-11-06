<template>
    <div class="card">
        <a href="/">
            <img class="img" :src="object.src" :alt="object.name">
            <p class="name">{{ object.name }}</p>
            <h2 class="desc" v-html="object.desc"></h2>
            <p class="location">{{ object.location }}</p>
            <p class="rent">{{ object.rent }}円〜 / 月</p>
        </a>
    </div>
</template>

<script>
    export default {
        props: {
            object: Object,
        }
    }
</script>

<style lang="scss" scoped>
    .card {
        letter-spacing: $ls-lg;
        font-weight: 500;
        background-color: $bg-clr-sub;
        padding: 15px 25px;
        transition: $trans-in;
        box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2);

        &:hover {
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
        }

        a {

            h2,
            p {
                margin-bottom: 3px;
            }

            .img {
                display: block;
                width: 100%;
                margin-bottom: 20px;
            }

            .name,
            .location {
                font-size: 1.2rem;
                
                @include mq(pc) {
                    font-size: 1.6rem;
                }
            }

            .name {
                display: inline-block;
                color: $clr-accent;
                border: solid 2px $clr-accent;
                padding: 3px 6px;

                @include mq(pc) {
                    padding: 6px 12px;
                }
            }

            .desc {
                line-height: $lh-200;
                font-size: 15px;

                @include mq(pc) {
                    font-size: 2rem;
                }
            }

            .location {
                --icon-size: 21px;

                color: $clr-accent;
                position: relative;
                padding-left: calc(var(--icon-size) + 6px);

                @include mq(pc) {
                    --icon-size: 27px;
                }

                &::before {
                    position: absolute;
                    top: -6px;
                    left: 0;
                    display: inline-block;
                    content: "";
                    width: var(--icon-size);
                    height: var(--icon-size);
                    background: url('~assets/img/icon-destination.svg') no-repeat;
                    background-size: contain;
                }
            }

            .rent {
                font-size: 2rem;
                color: $clr-main;
                font-weight: bold;
                margin-top: 20px;

                @include mq(pc) {
                    font-size: 2.4rem;
                }
            }
        }
    }
</style>