<template>
    <div class="inquiry" :class="{ 'simple': mode.simple }">
        <div v-if="mode.simple !== true" class="title">
            <span>CONTACT</span>
            <h2>お問い合わせ</h2>
        </div>
        <div class="grid-wrapper">
            <div
                v-if="!mode.simple || mode.displaySection === 'email'"
                class="email"
            >
                <h3>物件の内見、入居希望はこちらから</h3>
                <InquiryButton :color-reversed="true">
                    お問い合わせフォームへ
                </InquiryButton>
                <p class="desc">翌営業日以内に必ず返信致します。</p>
            </div>
            <div
                v-if="!mode.simple || mode.displaySection === 'tel'"
                class="tel"
            >
                <h3>
                    電話でのお問い合わせにも<br>
                    対応しております
                </h3>
                <Tel :color-reversed="true" /> <!-- class="tel" -->
                <p class="day-off"><span>定休日 /</span> 土日祝</p>
                <p class="opening-hours"><span>営業時間 /</span> 9:00 ~ 18:00</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        mode: {
            type: Object,
            'default': () => ({
                simple: false
            })
        }
    }
}
</script>

<style lang="scss" scoped>
    .inquiry {
        letter-spacing: $ls-xl;
        padding: 65px 0;
        background-color: $clr-main;
        color: $bg-clr-sub;
        text-align: center;

        .title {
            margin-bottom: 50px;
            font-weight: 500;

            h2 {
                font-size: 28px;
                line-height: $lh-150;
            }
        }

        .grid-wrapper {
            display: grid;
            grid-template-columns: 1fr;

            @include mq(pc) {
                grid-template-columns: 1fr 1fr;
            }

            h3 {
                font-weight: 500;
                line-height: $lh-150;
            }

            .email,
            .tel {
                padding: 25px 0;
            }

            .email {
                --border-style: 2px solid #fff;
                
                margin-bottom: 40px;
                
                @include mq(pc) {
                    margin-bottom: 0;
                    border-right: var(--border-style);
                }
                
                .btn-inquiry {
                    margin-top: 40px;
                    margin-bottom: 20px;
                }

                .desc {
                    font-size: 14px;
                }
            }
            
            // 親要素から子要素のcssを変更するときは"::v-deep"をつける
            ::v-deep .tel-number {
                justify-content: center;
                font-size: 32px;
                margin: 25px 0;

                span {
                    --icon-size: 40px;
                }
            }

            .day-off,
            .opening-hours {
                font-weight: 500;

                @include mq(pc) {
                    display: inline-block;
                    
                }

                span {
                    font-weight: 400;
                    font-size: 12px; 
                }
            }

            .day-off {
                @include mq(pc) {
                    margin-right: 15px;
                }
            }
        }

        &.simple {
            padding: 20px 0;

            .grid-wrapper {
                @include mq(pc) {
                    grid-template-columns: 1fr;
                }
            }
        }
    }
</style>