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
        <ul>
            <li v-for="(elem, index) in navElem" :key="index" :class="elem.current ? 'active' : ''">
                <a :href="elem.link"> {{ elem.text }} </a>
            </li>
        </ul>   
    </div>
   </header> 
</template>

<style lang="scss" scoped>
@use '../style/partials/mixins' as *;
.container{
    @include container(80%);
    @include flex(row,space-between,stretch);

    ul{
        list-style-type: none;
        @include flex(row,center,center);

        li{
            margin: 0 .5rem;
            height: 100%;
            display: flex;
            
            a{
                text-decoration: none;
                color: inherit;
                align-self: center;
                
            }

            &.active,
            &:hover{
                color: #0282F9;
                border-bottom: 5px solid #0282F9;
            }
        }
    }
}
</style>