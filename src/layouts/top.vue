<template>
    <!-- 
        topページではページの途中にお問い合わせセクションを入れたいので、
        カスタムレイアウトを作成 
    -->

    <div class="wrapper">
        <Header />
        <main>
            <Nuxt />
            <!-- <Inquiry /> -->
        </main>
        <Footer />
    </div>
</template>

<style lang="scss" scoped>
    .wrapper {
        background-color: $bg-clr-main;
    }
</style>