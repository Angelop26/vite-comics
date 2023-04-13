<script>
    export default{
        name: 'AppHeader',
        data(){
            return{
                navElem:[
                    {
                    link: '#',
                    text: 'characters',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'comics',
                    current: true
                    },
                    {
                    link: '#',
                    text: 'movies',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'tv',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'games',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'collectibles',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'videos',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'fans',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'news',
                    current: false
                    },
                    {
                    link: '#',
                    text: 'shop',
                    current: false
                    }
                ]
            }
        }
    }
</script>

<template>
   <header>
    <div class="container">
        <div class="header-logo">
            <a href="">
                <img src="../assets/img/dc-logo.png" alt="">
            </a>
        </div>
        <nav>
            <ul>
                <li v-for="elem in navElem" >
                    <a :href="elem.link" :class="elem.current ? 'active' : ''"> {{ elem.text }} </a>
                </li>
            </ul>
        </nav>
    </div>
   </header> 
</template>

<style lang="scss" scoped>
@use '../style/partials/mixins' as *;
.container{
    width: 60%;
    margin: 0 auto;
    @include flex(row,space-between,center);

    ul{
        list-style-type: none;
        @include flex(row,center,center);

        li{
            margin: 0 .5rem;

            a{
                text-decoration: none;
                color: black;
    
                &.active,
                &:hover{
                    color: #0282F9;
                }
            }
        }
    }
}
</style>