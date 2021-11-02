<template>
    <div>
        <ContentWrapper>
            <div class="kv">
                <h1>Change your life from home.</h1>
                <div class="box">
                    <h2>暮らしを、家から</h2>
                    <p>私たちは都内での暮らしを豊かにします。私たちは都内での暮らしを豊かにします。<br>
                        入居者、随時募集中！</p>
                </div>
            </div>
            <div class="apartments">
                <CardWrapper :objects="apartments" />
            </div>
        </ContentWrapper>
        <Inquiry />
        <ContentWrapper>
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
        </ContentWrapper>
        <HeroWrapper :objects="heros" />
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
                        desc: '渋谷・新宿へ出やすいメゾネットアパート',
                        location: '世田谷区 経堂',
                        rent: '70,000'
                    },
                    {
                        name: 'UVAS三軒茶屋',
                        src: require('~/assets/img/uvas-kyodo.jpg'),
                        desc: '渋谷まで電車で〇〇分の学生用アパート',
                        location: '世田谷区 三軒茶屋',
                        rent: '70,000'
                    },
                    {
                        name: 'UVAS西馬込',
                        src: require('~/assets/img/uvas-kyodo.jpg'),
                        desc: '横浜まで電車で〇〇分の好アクセス',
                        location: '大田区 南馬込',
                        rent: '70,000'
                    },
                    {
                        name: '大井町AP',
                        src: require('~/assets/img/uvas-kyodo.jpg'),
                        desc: '品川駅までわずか2駅の社会人向けアパート',
                        location: '品川区 東大井',
                        rent: '90,000'
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
            display: none;

            @include mq(pc) {
                display: block;
                font-size: 40px;
                letter-spacing: $ls-lg;
                margin-bottom: 40px;
                z-index: 1;
            }
        }

        .box {
            width: clamp(250px, 70vw, 480px);
            margin-right: 10px;
            z-index: 1;
            grid-column: 2 / 3;
            grid-row: 2 / 3;

            letter-spacing: $ls-xl;
            line-height: $lh-200;

            @include mq(pc) {
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