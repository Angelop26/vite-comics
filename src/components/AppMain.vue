<script>
import ListCard from "./ListCard.vue"

export default{
    name:'AppMain',
    components:{
        ListCard
    },
    data(){
        return{
            BottomBanner:[
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
            ],
            series:[
                {
                    thumb: 'https://www.coverbrowser.com/image/action-comics/1-1.jpg',
                    price: '$19.99',
                    series: 'Action Comics',
                    type: 'comic book',
                },
                {
                    thumb: 'https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg',
                    price: '$3.99',
                    series: 'American Vampire 1976',
                    type: 'comic book',
                },
                {
                    thumb: 'https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg',
                    price: '$16.99',
                    series: 'Aquaman',
                    type: 'graphic novel',
                },
                {
                    thumb: 'https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg',
                    price: '$2.99',
                    series: 'Batgirl',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg',
                    price: '$3.99',
                    series: 'Batman',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg',
                    price: '$2.99',
                    series: 'Batman Beyond',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg',
                    price: '$3.99',
                    series: 'Batman/Superman',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg',
                    price: '$4.99',
                    series: 'Batman/Superman Annual',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg',
                    price: '$5.99',
                    series: 'Batman: The Joker War Zone',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg',
                    price: '$6.99',
                    series: 'Batman: Three Jokers',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg',
                    price: '$4.99',
                    series: 'Batman: White Knight Presents: Harley Quinn',
                    type: 'comic book',
                },
                {
                    thumb: 'https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg',
                    price: '$16.99',
                    series: 'Catwoman',
                    type: 'graphic novel',
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
        <div class="jumbotron">
        </div>
        <section class="main">
            <h3 class="main-title">CURRENT LIST</h3>
            <div class="main-container">
                <div class="row">
                    <ListCard v-for="(serie, index) in series" :key="index" :thumb="serie.thumb" :series="serie.series"/>
                </div>
                <a href="#">Load More</a>
            </div>
        </section>
        <section class="bottomBanner">
            <div class="container">
                <ul>
                    <li v-for="(item,index) in BottomBanner" :key="index ">
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
        <section class="bottom">
            <div class="bottom-container">
                <div class="row">
                    <div class="col">
                        <h3>DC COMICS</h3>
                        <ul>
                            <li>Characters</li>
                            <li>Comics</li>
                            <li>Movies</li>
                            <li>TV</li>
                            <li>Games</li>
                            <li>Videos</li>
                            <li>News</li>
                        </ul>
                        <h3>SHOP</h3>
                        <ul>
                            <li>Shop DC</li>
                            <li>Shop DC Collectibles</li>
                        </ul>
                    </div>
                    <div class="col">
                        <h3>DC</h3>
                        <ul>
                            <li>Terms of Use</li>
                            <li>Privacy policy</li>
                            <li>Ad Choice</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                        </ul>
                    </div>
                    <div class="col">
                        <h3>SITES</h3>
                        <ul>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                            <li>lorem</li>
                        </ul>
                    </div>
                </div>
                <div class="logo-bottom">
                    <img src="../assets/img/dc-logo-bg.png" alt="">
                </div>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
@use '../style/partials/mixins' as*;

.jumbotron{
    height: 400px;
    background-image: url('../assets/img/jumbotron.jpg');
    background-size: cover;
    background-repeat: no-repeat;
}

.container{
    @include container(80%);
    padding: 3rem;
    .example{
        color: white;
    }
}


.main{
    background-color: #1c1c1c;
    padding-bottom: 2rem;

    &-title{
        background-color: #0282F9;
        color: white;
        width: fit-content;
        padding: 1rem;
        position: relative;
        top: -30px;
        left: 10%;
    }
    .main-container{
        @include container(80%);
        padding: .5rem;
        
        .row{
            @include flex(row,space-around,center); 
            flex-wrap: wrap;  
        }

        a{
            color: white;
            background-color: #0282F9;
            padding: 10px 20px;
            position: relative;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
    }
}
.bottomBanner{
    background-color: #0282F9;
    ul{
        @include flex(row,space-around,center);
        
        li{
            @include flex(row,flex-start,center);
            color: white;
        }
    }

    .img-container{
        margin-right: 1rem;
        img{
            height: 50px;
            max-width: 50px;
        }
    }
}

.bottom{
    width: 100%;
    background-image: url(../assets/img/footer-bg.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    .bottom-container{
        @include flex(row,space-between,center);
        @include container(80%)
    }
    .row{
        @include flex(row,flex-start,flex-start);
        width: 40%;
        h3{
            color: white;
        }
        ul{
            margin-right: 2rem;
            margin-bottom: .4rem;
            li{
                color: #889595;
            }
        }
    }
    .logo-bottom{
        height: 400px;
        width: 40%;
        img{
            object-fit: cover;
            height: 100%;
            width: 100%;
        }
    }
}
</style>