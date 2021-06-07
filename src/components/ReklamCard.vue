<template>
    <div class="wrapper">
        <div>
            <a :href="productLink">{{productTitle}}</a>
        </div>
        <div>
            <a :href="productLink">
              <img :src="imageSrc" alt="picture">
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name : "ReclamCard",
        props: {
            imageSrc: {
                type: String,
                default: 'https://bytes.ua/wp-content/uploads/2017/08/no-image.png'
            },
            productTitle:{
                type: String,
                default:'no title'
            },
            productLink:{
                type: String,
                default:'https://www.ukr.net/'
            },
        }
    }
</script>

<style lang="css" scoped>
.wrapper {
    width: 400px;
    height: 200px;
    border: 2px solid black;
    border-radius: 2px;
}
</style>