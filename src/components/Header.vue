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
        padding-left: 15px;
        position: sticky;
        top: 0;
        z-index: 100;

        .logo {
            display: flex;
            align-items: center;
        }
    }
</style>