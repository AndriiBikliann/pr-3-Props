<template>
  <div id="app">
    <!--<product-card
      image-src="https://content2.rozetka.com.ua/goods/images/preview/116580856.jpg"
      product-title="Монитор 23.8 Asus VA24EHE"
      product-link="https://hard.rozetka.com.ua/asus_90lm0560_b01170/p184066457/"
      product-price="3819грн."
    />-->
    <product-card v-for="(item,index) in productList" :key="index"
         :image-src="item.imageSrc"
         :product-title="item.productTitle"
         :product-link="item.productLink"
         :product-price="item.productPrice"     
         :is-in-store="item.isInStore"
      />
    <reclam-card
       image-src="data:image/jpeg;base64,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"
       product-title="У Києві знайдено стародавній рецепт відновлення зору"
       product-link="https://uk.wikipedia.org/wiki/%D0%93%D0%BE%D1%81%D1%82%D1%80%D0%BE%D1%82%D0%B0_%D0%B7%D0%BE%D1%80%D1%83"
    />
    <h2>Список студентів</h2>
    <student-list :data-arr="students"> 

    </student-list>
    <currency-exchenge
      v-for="item in exchangeRates" :key="item.id"
      :currency-name="item.name"
      :rating="item.rating"
    >
    </currency-exchenge>
  </div>
</template>

<script>
import ProductCard from './components/ProductCard.vue'
import ReclamCard from './components/ReklamCard.vue'
import StudentList from './components/StudentList.vue'
import CurrencyExchenge from './components/CurrencyExchenge.vue'

export default {
  name: 'App',
  components: {
    ProductCard,
    ReclamCard,
    StudentList,
    CurrencyExchenge,
  },
   data() {
   
     return {
      productList: [
        {   
          id:1,           
          imageSrc:"https://content2.rozetka.com.ua/goods/images/preview/116580856.jpg",
          productTitle:"Монитор 23.8 Asus VA24EHE",
          productLink:"https://hard.rozetka.com.ua/asus_90lm0560_b01170/p184066457/",
          productPrice:"3819грн."
        },
        {   
          id:2,           
          imageSrc:"https://content2.rozetka.com.ua/goods/images/preview/15611369.jpg",
          productTitle:"Процессор AMD Ryzen 5 3600",
          productLink:"https://hard.rozetka.com.ua/amd_ryzen_5_3600/p100191625/",
          productPrice:"6659",
          isInStore:false
        }, 
      ],
      students: [
        { id: 1, name: "Іванов І.І." },
        { id: 2, name: "Петров П.П." },
        { id: 3, name: "Степанов С.С." },
        { id: 4, name: "Воронін А.С." },
      ],
      exchangeRates: [
        { id: 1, name: "Долар", rating: 27 },
        { id: 2, name: "Євро", rating: 33 },
      ],
    }
  }
}
</script>

<style> </style>
