<script>
    import PageEmail from './PageEmail.vue'
    export default{
        components:{
            PageEmail
        }
    }
</script>

<template>
    <div class="wrap">

        <img src="../assets/images/logo.svg" alt="Logo">
        
        <h1>
            <span class="color-header">
                We're 
            </span>
            <span>
                coming 
            </span>
            <span>
                soon
            </span>
        </h1>
        <p>
            Hello fellow shoppers! We're currently building our new fashion store. 
            Add your email below to stay up-to-date with announcements and our launch deals.
        </p>
        <PageEmail></PageEmail>
    </div>
    
</template>

<style scoped>
    


    span{
        display: block;
    }
    img{
        width: max(30%, 200px);
    }
    .color-header{
        color: hsl(0, 36%, 70%);
    }
    p{
        font-size: 1.2rem;
        color: hsl(0, 93%, 68%);
    }

    @media (max-width: 1300px) {
        .wrap{
            display: flex;
            flex-direction: column;
            gap: 20px;
            justify-content: space-around ;
        }
    }
    
    @media (max-width: 850px) {
        img{
            display: none;
        }
        h1, p{
            text-align: center;
        }
        p{
            padding-inline: 3rem;
        }
    }
    @media (max-width: 850px) {
        p{
            padding-inline: unset;
        }
    }

</style>