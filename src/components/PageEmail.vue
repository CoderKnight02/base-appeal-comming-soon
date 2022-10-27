<script>

    export default{
        data(){
            return{
                msg: '',
                isemail: true,
                clickedOnce: false,
                cosas: 'haciendo cosas'
            }
        },
        methods:{
            isEmail(){

                if(
                    this.msg.length == 0 ||
                    this.msg.trim().includes(' ') ||
                    this.msg.indexOf('@') == -1 || 
                    this.msg.match(/@/g).length != 1 || 
                    this.msg.indexOf('.') == -1 || 
                    this.msg.match(/\./g).length != 1 ||
                    this.msg.indexOf('.') < this.msg.indexOf('@') ||
                    this.msg.search(/\.([a-z]|[0-9])/) == -1 || 
                    this.msg.search(/@([a-z]|[0-9])/) == -1 
                ){
                    this.isemail = false
                    setTimeout(() => {
                        document.getElementById('faded').classList.toggle('regular')
                    }, 2000);
                    document.getElementById('faded').classList.toggle('regular')
                } else {
                    this.isemail = true
                    this.num = 'esoy ejecutando el if return it true'
                } 
                if(!this.clickedOnce) {
                    this.clickedOnce = true
                }
            },
            
        },
        computed:{
            errorEmail(){
                return !this.isemail
            }
        }
    }

</script>

<template>
    
    
    <form action="#" :class="{'danger' : errorEmail}">
        <input required type="email" placeholder="Email Address" v-model="msg">
        <img src="../assets/images/icon-error.svg" class="icon-error" :class="{'icon-error-show' : errorEmail}" alt="!">
        <button @click.prevent="isEmail">
            <img src="../assets/images/icon-arrow.svg"  alt=">"> 
        </button>
    </form>    
    <p id="faded" class="invisible"> Plase provide a valid email </p>

</template>

<style scoped>
    button{
        padding: 10px;
        border:none;
        background: linear-gradient(135deg, hsl(0, 80%, 86%), hsl(0, 74%, 74%));
        border-radius: 9999px;
        width: 70px;
        cursor: pointer;
    }
    button:hover{
        transition: .2s;
        background: linear-gradient(135deg, hsl(0, 80%, 86%) 60%, hsl(0, 74%, 74%));
        box-shadow: 1px 1px 10px rgba(56, 15, 15, 0.562);
    }
    input{
        width: 70%;
        padding: 10px;
        border: none;
        background-color: transparent;
    }
    input:focus{
        outline: none;
    }
    
    form{
        padding-left: 10px;
        gap: 10px;
        display: flex;
        justify-content: space-between;
        align-items:center ;
        outline:1px solid hsl(0, 6%, 24%);
        border-radius: 9999px;
    }

    .regular{
        transform: translateX(0) !important;
        opacity: 1 !important;
    }
    .invisible{
        color: hsl(0, 93%, 68%);
        transition: all .2s;
        opacity: 0;
        transform: translateX(20px);
    }

    .danger{
        outline:2px solid red;
    }

    .icon-error-show{
        opacity: 1 !important;
        transform: translateX(0) !important;
    }
    .icon-error{
        transition: all .2s;
        opacity: 0;
        transform: translateX(20px);
    }
</style>