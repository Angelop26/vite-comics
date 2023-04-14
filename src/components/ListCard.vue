<script>
export default{
    name: 'ListCard',
    props:{
        thumb: String,
        series: String
    }
}
</script>

<template>
    <div class="col">
        <div class="img-container">
            <img :src="thumb" alt="">
        </div>
        <h4> {{ series }} </h4>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/mixins' as*;

.col{
    margin-right: 1rem;
    color: white;
    width: calc(100% / 6 - 1rem);
    margin-bottom: 1rem;
    height: 300px;
    .img-container{
        width: 100%;
        height: 80%;
        margin-bottom: 1rem;
    }
    img{
        object-fit: cover;
        object-position: top;
        width: 100%;
        height: 100%;
    }
}

</style>