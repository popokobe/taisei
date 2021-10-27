<template>
    <ul>
        <li><a href="/">物件一覧</a></li>
        <li><a href="/">事業内容</a></li>
        <li><a href="/">会社概要</a></li>
        <li class="inquiry">
            <a href="/">
                <span class="icon"></span>
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
        font-weight: 500;

        &:not(*:last-child) {
            margin: 20px 0;
            margin-right: 20px;
        }

        &.inquiry {
            display: flex;
            align-items: center;
            height: 100%;
            background-color: $clr-main;
            color: $bg-clr-sub;
            padding: 17px 12px;

            a {
                display: flex;
                flex-direction: column;
                align-items: center;

                span {
                    --icon-size: 28px;

                    font-size: 12px;

                    &.icon {
                        margin-bottom: 4px;
                        height: var(--icon-size);
                        width: var(--icon-size);
                        background-size: cover;
                        background-image: url('~assets/img/icon-mail-white.png');
                    }
                }
            }
        }

        a {
            letter-spacing: $ls-lg;
        }
    }
}
</style>