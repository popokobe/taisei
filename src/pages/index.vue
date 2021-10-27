<template>
    <div>
        <ContentWrapper class="apartments">
            <CardWrapper :objects="apartments" />
        </ContentWrapper>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                apartments: [
                    {
                        name: 'UVAS経堂',
                        src: 'https://placehold.jp/300x150.png',
                        desc: '渋谷・新宿へ出やすいメゾネットアパート',
                        location: '世田谷区 経堂',
                        rent: '70,000'
                    },
                    {
                        name: 'UVAS三軒茶屋',
                        src: 'https://placehold.jp/300x150.png',
                        desc: '渋谷まで電車で〇〇分の学生用アパート',
                        location: '世田谷区 三軒茶屋',
                        rent: '70,000'
                    },
                    {
                        name: 'UVAS西馬込',
                        src: 'https://placehold.jp/300x150.png',
                        desc: '横浜まで電車で〇〇分の好アクセス',
                        location: '大田区 南馬込',
                        rent: '70,000'
                    },
                    {
                        name: '大井町AP',
                        src: 'https://placehold.jp/300x150.png',
                        desc: '品川駅までわずか2駅の社会人向けアパート',
                        location: '品川区 東大井',
                        rent: '90,000'
                    },
                ]
            }
        }
    }
</script>

<style lang="scss" scoped>
</style>