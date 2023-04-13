<script>
export default{
    name:'AppMain',
    data(){
        return{
            mainMenu:[
                {
                    img:'buy-comics-digital-comics.png',
                    text: 'DIGITAL COMICS'
                },
                {
                    img:'buy-comics-merchandise.png',
                    text: 'DC MERCHANDISE'
                },
                {
                    img:'buy-comics-subscriptions.png',
                    text: 'SUBSCRIPTION'
                },
                {
                    img:'buy-comics-shop-locator.png',
                    text: 'COMIC SHOP LOCATOR'
                },
                {
                    img:'buy-dc-power-visa.svg',
                    text: 'DC POWER VISA'
                },
            ]
        }
    },
    methods:{
        getImgPath(name) {
            return new URL(`../assets/img/${name.img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <main>
        <section class="main">
            <div class="container">
                <h1 class="example"> --> Content goes here &lt;--</h1>
            </div>
        </section>
        <section class="cta">
            <div class="container">
                <ul>
                    <li v-for="item in mainMenu">
                        <div class="img-container">
                            <img :src="getImgPath(item)" alt="">
                        </div>
                        <span>
                            {{ item.text }}
                        </span>
                    </li>
                </ul>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/mixins' as*;
.main{
    background-color: black;
}
.container{
    width: 60%;
    margin: 0 auto;
    padding: 3rem;
    .example{
        color: white;
    }
}

.cta{
    background-color: #0282F9;
    ul{
        @include flex(row,space-around,center);
    }

    li{
        @include flex(row,flex-start,center);
        color: white;
    }
    .img-container{
        width: 20%;
        margin-right: 1rem;
    }
}
</style>