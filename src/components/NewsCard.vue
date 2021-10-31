<template>
    <li class="news-item">
        <a :href="item.slug">
            <img :src="item.src" :alt="item.title">
            <span class="tag">{{ item.tag }}</span>
            <span class="date">{{ item.date }}</span>
            <h3>{{ item.title }}</h3>
            <p>
                {{ item.body }}
            </p>
        </a>
    </li>
</template>

<script>
export default {
    props: {
        item: Object
    }
}
</script>

<style lang="scss" scoped>
.news-item {
    width: clamp(250px, 60%, 350px);
    flex-shrink: 0;
    padding: 25px 20px 40px;
    box-shadow: 0 2px 4px 0 rgb(0 0 0 / 20%);
    background: $bg-clr-sub;
    border-radius: 3%;
    font-weight: 500;

    @include mq(pc){
        width: clamp(250px, 40%, 350px);
    }

    &:not(:last-child) {
        margin-right: 15px;
    }


    img {
        width: 100%;
        margin-bottom: 13px;
        height: 150px;
        object-fit: cover;
    }

    span.tag {
        color: $bg-clr-sub;
        background-color: $clr-main;
        padding: 2px 5px;
        font-size: 15px;
    }
    
    h3 {
        line-height: $lh-200;
    }

    p {
        font-weight: 400;
        line-height: $lh-150;
    }
}
</style>