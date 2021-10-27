<template>
    <li>
        <a v-if="icon == 'instagram'" class="instagram" target="_blank" href="https://www.instagram.com/taisei.1996131/"></a>
        <a v-if="icon == 'tiktok'" class="tiktok" target="_blank" href="https://www.tiktok.com/@taisei1996131?"></a>
    </li>
</template>

<script>
export default {
    props: {
        icon: String
    }
}
</script>

<style lang="scss" scoped>

    a {
        --icon-size: 30px;
        
        display: block;
        width: var(--icon-size);
        height: var(--icon-size);

        &.instagram {
            background: url('~assets/img/icon-instagram.png') no-repeat;
            background-size: cover;
        }

        &.tiktok {
            background: url('~assets/img/icon-tiktok.png') no-repeat;
            background-size: cover;
        }
    }

</style>