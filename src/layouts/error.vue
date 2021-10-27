<template>
    <div class="wrapper">
        <div>
            <h1>ページが見つかりませんでした。</h1>
            <p><a href="/">ホーム</a>に戻る</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .wrapper {
        height: 400px;
        text-align: center;
        display: grid;
        place-items: center;

        h1 {
            margin-bottom: 30px;
        }

        a {
            text-decoration: underline;
            color: $clr-main;
        }
    }
</style>