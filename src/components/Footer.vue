<template>
    <footer>
        <ContentWrapper>
            <div class="grid-wrapper">
                <div>
                    <Logo />
                    <div class="address">
                        <span class="zip-code">〒 160-0801</span>
                        <p>東京都新宿区山吹町337-5<br>
                            都住創山吹町ビル9階</p>
                    </div>
                </div>
                <div class="link">
                    <ul class="link-wrapper">
                        <li><a href="">HOME</a></li>
                        <li><a href="">賃貸物件一覧</a></li>
                        <li><a href="">新着情報</a></li>
                    </ul>
                    <hr>
                    <ul class="link-wrapper">
                        <li><a href="">事業内容</a></li>
                        <li><a href="">会社概要</a></li>
                    </ul>
                </div>
                <div>
                    <Tel />
                    <p class="day-off"><span>定休日 /</span> 土日祝</p>
                    <p class="opening-hours"><span>営業時間 /</span> 9:00 ~ 18:00</p>
                    <InquiryButton />
                    <div class="sns-wrapper">
                        <span>各種SNS：</span>
                        <SnsWrapper :sns="['instagram', 'tiktok']" />
                    </div>
                </div>
            </div>
            <p class="copyright">copyright © 株式会社タイセイ All Rights Reserved.</p>
        </ContentWrapper>
    </footer>
</template>

<style lang="scss" scoped>
    footer {
        letter-spacing: $ls-lg;

        .content-wrapper {
            padding: 25px 0 10px;
            
            @include mq(pc) {
                padding-top: 60px;
            }

            .grid-wrapper {
                display: grid;
                grid-template-rows: 1fr;
                grid-template-columns: 1fr;

                @include mq(pc) {
                    grid-template-columns: 1fr 160px 270px;
                }

                .address {
                    font-weight: 500;
                    margin: 20px 0;
                    line-height: $lh-150;

                    @include mq(pc) {
                        margin: 0;
                        margin-top: 40px;
                    }

                    .zip-code {
                        display: block;
                    }
                }

                .link {
                    margin-bottom: 30px;

                    @include mq(pc) {
                        margin-bottom: 0;
                    }
                    
                    ul.link-wrapper {
                        font-size: 14px;
                        font-weight: 500;

                        &+hr {
                            width: 100px;
                            margin: 20px 0;
                        }

                        li {
                            line-height: $lh-200;
                        }
                    }
                }

                .day-off,
                .opening-hours {
                    margin-top: 15px;
                }

                .sns-wrapper {
                    display: flex;
                    align-items: center;
                }

                .btn-inquiry {
                    margin: 25px 0;
                }
            }

            .copyright {
                font-size: 10px;
                margin-top: 40px;
                text-align: center;

                @include mq(pc) {
                    text-align: right;
                }
            }
        }
    }
</style>