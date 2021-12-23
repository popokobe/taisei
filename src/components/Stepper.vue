<template>
    <div class="stepper-box">
        <div class="top">
            <div class="divider-line"></div>
            <div class="steps-wrapper">
                <template v-for="(step, index) in steps">
                    <div :key="index" class="step">
                        <div class="circle">
                            <i class="material-icons">
                                {{ (step.completed) ? 'done' : step.icon }}
                            </i>
                        </div>
                        <div class="step-title">
                            <h4>{{ step.title }}</h4>
                        </div>
                    </div>
                </template>
            </div>
        </div>
        <transition name="slide">
            <FormGroup v-if="show" class="form" @confirm="toggle" />
            <h1 style="margin: 50px 0;" v-if="!show">入力確認ページ</h1>
        </transition>
    </div>
</template>

<script>
    export default {
        props: {
            steps: {
                type: Array,
                default: () => []
            }
        },
        data () {
            return {
                show: true
            }
        },
        methods: {
            toggle() {
                this.show = !this.show
            }
        }
    }
</script>

<style lang="scss" scoped>
    .stepper-box {
        @include mq(pc) {
            width: 80%;
            margin: 0 auto;
        }

        .top {
            display: flex;
            align-items: center;
            position: relative;
            justify-content: center;

            .divider-line {
                border-bottom: 1px solid $border-clr-main;
                width: 90%;
                height: 2px;
                position: absolute;
            }

            .steps-wrapper {
                display: flex;
                justify-content: space-between;
                width: 95%;

                .step {
                    position: relative;
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    text-align: center;

                    .circle {
                        margin-bottom: 1rem;
                        padding: 0 1rem;
                        background-color: $bg-clr-main;

                        i {
                            background-color: $clr-main;
                            color: $bg-clr-sub;
                            border-radius: 50%;
                            padding: 1rem;
                        }
                    }

                    .step-title {
                        position: absolute;
                        top: 90%;
                        width: 100%;

                        h1,
                        h2,
                        h3,
                        h4,
                        h5 {
                            margin: 0 0 .2rem 0;
                            font-weight: bold;
                        }
                    }
                }


            }
        }
        
        .form {
            margin: 50px 0;
        }

        .slide-enter-active,
        .slide-leave-active {
            transition: opacity .5s;
        }

        .slide-enter,
        .slide-leave-to {
            opacity: 0;
        }
    }
</style>