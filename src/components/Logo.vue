<template>
    <div class="logo">
        <a href="/">
            <img src="~/assets/img/logo.jpg">
            <div class="text">
                <span class="sub">株式会社ポポ</span>
                <span class="main">POPO GROUP</span>
            </div>
        </a>
    </div>
</template>

<style lang="scss" scoped>
    .logo {
        color: $clr-main;

        a {
            display: flex;
            align-items: center;

            img {
                --icon-size: 30px;
                
                @include mq(tab) {
                    --icon-size: 45px;
                }

                width: var(--icon-size);
                height: var(--icon-size);
                margin-right: 5px;
            }

            .text {
                span {
                    display: block;
                    letter-spacing: $ls-md;
                    line-height: $lh-125;

                    &.sub {
                        font-size: 8px;

                        @include mq(tab) {
                            font-size: 12px;
                        }  
                    }

                    &.main {
                        font-size: 14px;
                        
                        @include mq(tab) {
                            font-size: 24px;
                        }
                    }
                }
            }
        }
    }
</style>