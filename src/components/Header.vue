<template>
    <header>
        <Logo />
        <Nav />
    </header>
</template>

<style lang="scss" scoped>
    header {
        background-color: $bg-clr-sub;
        display: flex;
        justify-content: space-between;
        padding-left: 5px;
        position: sticky;
        top: 0;
        z-index: 100;
        height: 60px;

        @include mq(tab) {
            height: 80px;
            padding-left: 15px;
        }

        .logo {
            display: flex;
            align-items: center;
            z-index: -2;
        }
    }
</style>