<template>
    <div>
      <table>
          
          <thead>
              <tr>
                <th>{{ firstTitle }}</th>
                <th>{{ secondTitle }}</th>
              </tr>
          </thead>
          
          <tbody>
              <tr>
                <td>{{ currencyName }}</td>
                <td>{{ rating }}</td>
              </tr>
          </tbody>

      </table>
    </div>
</template>

<script>
    export default {
        name: 'CurrencyExchenge',
        props: {
            firstTitle: {
                type:String,
                default:"Назва валюти"
            },
            secondTitle: {
                type:String,
                default:"Курс у гривні"
            },
            currencyName: {
                type:String,
                default:"currency of the country"
            },
            rating: {
                type:Number,
                default: 1
            }
        }

    }
</script>

<style lang="css" scoped>
 table,th,td {
     border: 1px solid #000;
 }
</style>