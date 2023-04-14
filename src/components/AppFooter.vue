<script>
export default{
    name:'AppFooter',
    data(){
       return{
        socials:[
            'footer-facebook.png',
            'footer-periscope.png',
            'footer-pinterest.png',
            'footer-twitter.png',
            'footer-youtube.png'
        ]
       } 
    },
    methods:{
        getImgPath(name) {
            return new URL(`../assets/img/${name}`, import.meta.url).href;
        }
    }

}
</script>

<template>
<footer>
    <div class="container">
        <div class="sign-up">SIGN-UP NOW</div>
        <div class="follow-us">
            <h3>FOLLOW US</h3>
            <img v-for="(elem,index) in socials" :key="index" :src="getImgPath(elem)" alt="">
        </div>
    </div>
</footer>
</template>

<style scoped lang="scss"> 
@use "../style/partials/mixins" as *;

footer{
    background-color: #303030;
    padding: 2rem;
    .container{
        @include container(80%);
        @include flex(row,space-between,center);
        
        .sign-up{
            border: 1px solid #0282F9;
            color: white;
            padding: 1rem;
        }
        .follow-us{
            @include flex(row,space-around,center);
            h3,
            img{
                margin-right: 1rem;
            }
    
            h3{
                color: #0282F9;
            }
    
        }
    }
}

</style>