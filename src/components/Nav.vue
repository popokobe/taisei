<template>
    <ul>
        <li><a href="/">物件一覧</a></li>
        <li><a href="/">事業内容</a></li>
        <li><a href="/">会社概要</a></li>
        <li class="inquiry">
            <a href="/">
                <span>お問い合わせ</span>
            </a>
        </li>
    </ul>
</template>

<style lang="scss" scoped>
ul {
    display: flex;
    align-items: center;

    li {
        &:not(*:last-child) {
            margin-right: 20px;
        }

        &.inquiry {
            display: flex;
            align-items: center;
            height: 100%;
            background-color: $clr-main;
            color: $bg-clr-sub;
        }
    }
}
</style>