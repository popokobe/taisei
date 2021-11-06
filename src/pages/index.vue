<template>
    <div>
        <ContentWrapper>
            <div class="kv">
                <div class="box">
                    <h1>TAISEISM</h1>
                    <h2>De-Domain</h2>
                    <p>
                        TAISEISM ともいうべき企業理念 「De-Domain」 (脱領域)には、いわれなき規制・指導 慣例など既存の領域から脱皮することで、 より
                        「公正」「正常」な社会の実現という意味がこめられています｡
                    </p>
                </div>
            </div>
            <div class="apartments">
                <CardWrapper :objects="apartments" />
            </div>
        </ContentWrapper>
        <Inquiry />
        
        <!-- 遷移先のページができ次第コメントアウトを解除してください -->
        <!-- <ContentWrapper>
            <div class="news">
                <div class="box">
                    <Heading :title="{ main: '新着情報', sub: 'NEWS' }" />
                    <p>物件に空きが出た場合や事業計画、その他お知らせ等をこちらに掲載します。物件に空きが出た場合や事業計画、その他お知らせ等をこちらに掲載します。</p>
                    <a href="/news">VIEW ALL</a>
                </div>
                <ul class="card-wrapper">
                    <NewsCard v-for="item in newsItems" :key="item.id" :item="item" />
                </ul>
            </div>
        </ContentWrapper> -->
        <!-- <HeroWrapper :objects="heros" /> -->
    </div>
</template>

<script>
    export default {
        layout: 'top',
        data() {
            return {
                apartments: [
                    {
                        name: 'UVAS経堂',
                        src: require('~/assets/img/uvas-kyodo.jpg'),
                        desc: '都会のオアシス 新宿まで急行で3駅',
                        location: '小田急線「経堂」駅より徒歩10分',
                        rent: '73,000'
                    },
                    {
                        name: 'UVAS三軒茶屋',
                        src: require('~/assets/img/uvas-sancha.jpg'),
                        desc: '人気の街 三軒茶屋駅より徒歩5分の好立地',
                        location: '田園都市線「三軒茶屋」駅より徒歩5分',
                        rent: '86,000'
                    },
                    {
                        name: 'UVAS西馬込',
                        src: require('~/assets/img/uvas-nishimagome.jpg'),
                        desc: '路線の始発駅なので座って通勤したい方に人気',
                        location: '都営浅草線「西馬込」駅より徒歩9分',
                        rent: '76,000'
                    },
                    {
                        name: '大井町AP',
                        src: require('~/assets/img/oimachi-ap.jpg'),
                        desc: '品川駅まで3分',
                        location: 'JR京浜東北線「大井町」駅より徒歩10分',
                        rent: '116,000'
                    },
                ],
                newsItems: [
                    {
                        slug: '/hello',
                        src: require('~/assets/img/hero-main.jpg'),
                        tag: '事業',
                        date: '2021.9.10',
                        title: 'M&A仲介サービスを開始',
                        body: '当社グループの一員となっていただける企業様、事業運営者様を探しております。これまでの実績としては飲食業界、不動産業界が多い……'
                    },
                    {
                        slug: '/hello',
                        src: require('~/assets/img/hero-main.jpg'),
                        tag: '事業',
                        date: '2021.9.10',
                        title: 'M&A仲介サービスを開始',
                        body: '当社グループの一員となっていただける企業様、事業運営者様を探しております。これまでの実績としては飲食業界、不動産業界が多い……'
                    },
                    {
                        slug: '/hello',
                        src: require('~/assets/img/hero-main.jpg'),
                        tag: '事業',
                        date: '2021.9.10',
                        title: 'M&A仲介サービスを開始',
                        body: '当社グループの一員となっていただける企業様、事業運営者様を探しております。これまでの実績としては飲食業界、不動産業界が多い……'
                    },
                    {
                        slug: '/hello',
                        src: require('~/assets/img/hero-main.jpg'),
                        tag: '事業',
                        date: '2021.9.10',
                        title: 'M&A仲介サービスを開始',
                        body: '当社グループの一員となっていただける企業様、事業運営者様を探しております。これまでの実績としては飲食業界、不動産業界が多い……'
                    },
                    {
                        slug: '/hello',
                        src: require('~/assets/img/hero-main.jpg'),
                        tag: '事業',
                        date: '2021.9.10',
                        title: 'M&A仲介サービスを開始',
                        body: '当社グループの一員となっていただける企業様、事業運営者様を探しております。これまでの実績としては飲食業界、不動産業界が多い……'
                    },
                ],
                heros: [
                    {
                        name: '会社概要',
                        href: '/about',
                        src: require('~/assets/img/hero-main.jpg')
                    },
                    {
                        name: '事業内容',
                        href: '/business',
                        src: require('~/assets/img/hero-main.jpg')
                    },
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
    .kv {
        margin: 0 calc(50% - 50vw);
        padding: 4px calc(50vw - 50%);
        width: 100vw;
        position: relative;
        display: grid;
        align-items: center;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        height: clamp(200px, 90vh, 600px);
        background: url("~/assets/img/kv.jpg") no-repeat;
        background-size: cover;
        color: $bg-clr-sub;
        overflow: hidden;

        &::before {
            position: absolute;
            content: "";
            display: block;
            width: 100%;
            height: 100%;
            background: rgba($clr-main, 0.8);

            @include mq(pc) {
                display: none;
            }
        }

        &::after {
            position: absolute;
            bottom: -250px;
            right: -225px;
            content: "";
            display: block;
            background: rgba($bg-clr-sub, 0.4);
            --diameter: 500px;
            width: var(--diameter);
            height: var(--diameter);
            border-radius: 50%;

            @include mq(tab) {
                bottom: -400px;
                --diameter: 700px;
            }

            @include mq(pc) {
                background: rgba($clr-main, 0.9);
                --diameter: clamp(900px, 90vw, 1150px);
                top: -400px;
                left: -400px;
            }

        }

        @include mq(pc) {
            background: url("~/assets/img/kv-pc.jpg") no-repeat;
            margin: auto;
            padding: 0;
            width: auto;
            grid-template-columns: none;
            grid-template-rows: none;
            background-position: top 50% right 0;
            background-size: 700px;
            overflow: visible;
            align-content: center;
        }

        h1 {
            font-style: italic;
            font-weight: 200;
            font-size: 40px;
            letter-spacing: $ls-lg;

            @include mq(pc) {
                margin-bottom: 10px;
            }
        }

        .box {
            width: clamp(250px, 70vw, 480px);
            margin-right: 10px;
            margin-bottom: 10px;
            z-index: 1;
            grid-column: 2 / 3;
            grid-row: 2 / 3;

            letter-spacing: $ls-xl;
            line-height: $lh-200;

            @include mq(pc) {
                margin-bottom: 0;
                width: clamp(300px, 70vw, 480px);
                grid-column: 1 / 2;
                grid-row: 2 / 3;
            }

            h2,
            p {
                font-weight: 300;
            }

            h2 {
                font-size: 27px;
            }

            p {
                font-size: 14px;
            }
        }
    }

    .apartments {
        position: relative;
        z-index: 2;
        margin: 60px 0;
    }

    .news {
        margin: 80px 0;

        @include mq(pc) {
            margin: 130px 0;
            display: flex;
        }

        .box {
            margin-bottom: 40px;
            letter-spacing: $ls-lg;
            text-align: center;

            @include mq(pc) {
                width: 50%;
                margin-right: 30px;
            }

            p {
                margin: 20px 0;
                text-align: left;
                line-height: $lh-150;
            }

            a {
                display: block;
                font-weight: 500;
                color: $clr-main;
                position: relative;

                &::after {
                    transition: $trans-in;
                    content: '';
                    display: inline-block;
                    position: absolute;
                    transform: translateX(-50%);
                    left: 50%;
                    bottom: -10px;
                    width: 45px;
                    height: 2px;
                    background-color: $clr-main;
                }

                &:hover {
                    &::after {
                        bottom: -7px;
                    }
                }
            }
        }

        .card-wrapper {
            display: flex;
            overflow-x: scroll;

            @include mq(pc) {
                width: 50%;
            }
        }
    }
</style>