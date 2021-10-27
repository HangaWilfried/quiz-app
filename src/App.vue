<script>
import Header from './components/Header.vue'
  import axios from 'axios'
  import {ref,onBeforeMount} from 'vue'

  export default{

    name: 'App',
    components: {
      Header
    },
    setup(){
      const index = ref(0)
      const items = ref([])

      onBeforeMount(()=>{
        axios.get('api.json').then((resolve)=>{
          items.value = resolve.data.results
        })
      })
      const update = ()=>index.value++
      return{
        index,
        update,
        items
      }
    }
  }
</script>



<template>
  <Header/>
<!--  <div v-for="(item, index) in items" :key="index" v-html="item.question"></div>-->
</template>



<style>
  /*div{*/
  /*  padding: 10px 20px;*/
  /*  background-color: #ffc068;*/
  /*  margin: 20px 30px;*/
  /*}*/
</style>


