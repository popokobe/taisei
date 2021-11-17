<template>
    <div class="page-header">
        <div class="box">
            <Heading :title="{ main: 'お問い合わせ', sub: 'INQUIRY' }" :color-reversed="true" />
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style lang="scss" scoped>
    .page-header {
        margin: 0 calc(50% - 50vw);
        padding: 4px calc(50vw - 50%);
        width: 100vw;
        position: relative;
        display: grid;
        align-items: center;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: 1fr 1fr;
        height: clamp(200px, 50vh, 600px);
        background: url("~/assets/img/kv.png") no-repeat;
        background-size: cover;
        overflow: hidden;

        &::before {
            position: absolute;
            content: "";
            display: block;
            width: 100%;
            height: 100%;
            background: rgba($clr-main, 0.8);
        }

        .box {
            grid-column: 1 / 2;
            grid-row: 2 / 3;

            position: absolute;
            bottom: 15px;
            left: 25px;

            @include mq(tab) {
                bottom: 25px;
                left: 40px;
            }
        }
    }
</style>