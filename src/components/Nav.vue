<template>
    <div class="menu-wrapper">
        <div class="hamburger-btn" @click="toggleMenu=!toggleMenu" :class="{ toggled : toggleMenu }">
            <span v-for="i in 3" :key="i.id" class="line" :class="'line-' + i">
            </span>
        </div>
        <ul :class="{ open : toggleMenu }">
            <li v-for="link in links" :key=link.id :class="[link.name === 'お問い合わせ' ? 'inquiry' : '']">
                <!-- "お問い合わせ"じゃない場合 -->
                <a v-if="link.name !== 'お問い合わせ'" :href="link.href">{{ link.name }}</a>

                <!-- "お問い合わせ"の場合 -->
                <a v-else :href="link.href">
                    <span class="icon"></span>
                    <span>お問い合わせ</span>
                </a>
            </li>
            <li v-if="toggleMenu">
                <InquiryButton />
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                toggleMenu: false,
                links: [
                    {
                        name: '物件一覧',
                        href: '/apartments'
                    },
                    {
                        name: '事業内容',
                        href: '/business'
                    },
                    {
                        name: '会社概要',
                        href: '/about'
                    },
                    {
                        name: 'お問い合わせ',
                        href: '/inquiry'
                    },
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
    .menu-wrapper {
        position: relative;

        .hamburger-btn {
            z-index: 100;
            cursor: pointer;
            height: 100%;
            width: 45px;

            @include mq(tab) {
                display: none;
            }

            .line {
                position: relative;
                display: block;

                &::before {
                    position: absolute;
                    left: 0;
                    right: 0;
                    margin: auto;
                    content: '';
                    display: block;
                    width: 24px;
                    height: 1.5px;
                    background: $clr-main;
                    transition: $trans-in;
                }

                &-1::before {
                    top: 20px;
                }

                &-2::before {
                    top: 30px;
                }

                &-3::before {
                    top: 40px;
                }

            }

            &.toggled {
                .line {
                    &-1::before {
                        transform: translateY(10px) rotate(-45deg);
                    }

                    &-2::before {
                        opacity: 0;
                    }

                    &-3::before {
                        transform: translateY(-10px) rotate(45deg);
                    }
                }
            }
        }

        ul {
            z-index: -1;
            overflow-x: hidden;
            transition: $trans-in;
            background: $bg-clr-sub;
            width: 0;
            height: 100vh;
            position: absolute;
            top: 0;
            right: 0;

            &.open {
                width: 80vw;
                padding: 45px 30px;
            }

            @include mq(tab) {
                position: static;
                width: auto;
                height: auto;
                display: flex;
                align-items: center;
            }

            li {
                font-weight: 500;

                &:not(*:last-child) {
                    margin: 25px 0;

                    @include mq(tab) {
                        margin: 20px 0;
                        margin-right: 20px;
                    }
                    
                }

                &.inquiry {
                    display: none;

                    @include mq(tab) {
                        display: flex;
                        align-items: center;
                        height: 100%;
                        background-color: $clr-main;
                        color: $bg-clr-sub;
                        padding: 17px 12px;
                    }

                    a {
                        display: flex;
                        flex-direction: column;
                        align-items: center;

                        span {
                            font-size: 12px;

                            @include mq(tab) {
                                --icon-size: 28px;
                            }

                            &.icon {
                                margin-bottom: 4px;
                                height: var(--icon-size);
                                width: var(--icon-size);
                                background-size: cover;
                                background-image: url('~assets/img/icon-mail-white.png');
                            }
                        }
                    }
                }

                a {
                    font-size: 18px;
                    letter-spacing: $ls-lg;

                    @include mq(tab) {
                        font-size: 16px;
                    }
                }
            }
        }
    }
</style>