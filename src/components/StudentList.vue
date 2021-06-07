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
        <tr v-for="(item, index) in dataArr" :key="item.id">
          <td>{{ index + 1 }}</td>
          <td>{{ item.name }}</td>
        </tr>
      </tbody>
    </table>

    <br />
  </div>
</template>
<script>
    export default {
        name :'StudentList',
        props : {
            firstTitle : {
               type: String,
               default:"№ п/п"
            },
            secondTitle : {
                type: String,
                default:"ПІБ",
            },
            dataArr : {
                type: Array,
                default:()=>[]
            }
        }
    }
</script>

<style lang="css" scoped>
table,tr,th {
    border: 1px solid black;
}
</style>