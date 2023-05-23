<script>
export default {
    props: {
        id: Number,
        name: String,
        type: String,
        img: String,
    }
}
</script>

<template>
    <div>
        <img :src="img" :alt="id">
        <span>{{ name }}</span>
        <span>{{ type }}</span>    
    </div>
    
</template>

<style lang="scss" scoped>
    div {
        display: flex;
        flex-direction: column;
        width: calc(100% / 5 - .3em);
        align-items: center;

        img {
            width: 100%;
        }
        span {
            max-width: max-content;
        }
    }
</style>