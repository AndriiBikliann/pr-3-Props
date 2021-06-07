<template>
   <div class="container">
        <div class="image">
            <a :href="productLink">
              <img :src="imageSrc" alt="product">
            </a>
        </div>
        <div>
            <a :href="productLink">{{productTitle}}</a>
        </div>
        <div>
            {{productPrice}}
        </div>
        <div>
            {{isAvailable}}
        </div>
    </div>

</template>

<script>
    export default {
        name :"ProductCard",
        props: {
            imageSrc: {
                type: String,
                default: 'https://bytes.ua/wp-content/uploads/2017/08/no-image.png'
            },
            productTitle:{
                type:String,
                default:'no title'
            },
            productLink:{
                type:String,
                default:'https://rozetka.com.ua/?gclid=Cj0KCQjwktKFBhCkARIsAJeDT0jznxz1wR7MVjDHE8Tkb2WKWXcPZql7PdyK2Oye3zD0_CF06KJdvjoaAiX-EALw_wcB'
            },
            productPrice:{
                type:[Number,String],
                default:null
            },
            isInStore:{
                type:Boolean,
                default:true
            }
        },
        computed: {
            isAvailable() {
                return this.isInStore?'У наявності':'Немає у наявності' 
            }
        },
    }
</script>

<style lang="css" scoped>

.container{
    color: red;
    display: inline-block;
    height: 300px;
    width: 150px;
    border: 2px solid green;
    border-radius: 8px;
}

</style>