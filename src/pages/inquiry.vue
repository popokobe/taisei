<template>
    <div class="inquiry">
        <PageHeader />
        <ContentWrapper>
            <p class="desc">内見、入居希望、その他各種質問等<br>
                お気軽にお問い合わせください。</p>
            <Stepper :steps="steps" />
        </ContentWrapper>
        <Inquiry :mode="inquiryMode" />
    </div>

</template>

<script>
    export default {
        data () {
            return {
                steps: [
                    {
                        title: "入力",
                        icon: "edit"
                    },
                    {
                        title: "確認",
                        icon: "visibility"
                    },
                    {
                        title: "完了",
                        icon: "done"
                    }
                ],
                inquiryMode: {
                    simple: true,
                    displaySection: 'tel'
                }
            }
        }
    }
</script>

<style lang="scss" scoped>
    .inquiry {
        .desc {
            text-align: center;
            font-weight: 500;
            line-height: $lh-150;
            margin: 40px 0;
        }
    }
</style>