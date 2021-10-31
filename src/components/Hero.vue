<template>
    <a class="hero" :href="object.href">
        <div class="content">
            <h2>{{ object.name }}</h2>
        </div>
        <img :src="object.src" :alt="object.name">
    </a>
</template>

<script>
export default {
    props: {
        object: Object,
    }
}
</script>

<style lang="scss" scoped>
.hero {
    display: grid;
    height: calc(250px + 25vmin);

    @include mq(tab) {
        height: 300px;
    }

    @include mq(pc) {
        height: calc(250px + 25vmin);
    } 

    &::after {
        content: "";
        background-color: #000;
        opacity: 0.75;
        grid-area: 1 / -1;
        transition: $trans-in;
    }
    
    &:hover {
        &::after {
            opacity: 0.6;
        }
    }

    & >* {
        grid-area: 1 / -1;
    }

    .content {
        color: $bg-clr-sub;
        z-index: 1;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        align-items: flex-end;
        padding: 20px;

        h2 {
            font-size: 24px;
            font-weight: 500;
        }
    }

    img {
        width: 100%;
        height: 100%;
        min-height: 0;
        object-fit: cover;
    }
}
</style>