<style scoped>
  header{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    grid-template-rows: repeat(2, 1fr);
  }
  #about-user{
    grid-column: 1/3;
    grid-row: 1/3;
    font-size: 22px;
    color: #ccc;
    background-color: #f5f5f5;
    text-align: center;
    display: flex;
    justify-content: space-between;
    padding: 0px 50px;
  }
  #about-user p{
    display: flex;
    align-items: center;
    gap: 5px;
    color: #005;
    font-size: 16px;
    margin-top: 30px;
  }
  #about-user p span{
    color: #009;
    background-color: #fff;
    border-radius: 15px;
    padding: 10px 20px;
    font-size: 17px;
  }
  #app-name{
    grid-column: 3/6;
    grid-row: 1/3;
    text-align: center;
    padding-top: 30px;
    z-index: 100;
    box-shadow: 1px 1px 3px #f2f2f2;
  }
  #given-name{
    grid-column: 5/5;
    grid-row: 1/3;
    text-align: center;
    padding-top: 30px;
    padding-bottom: 10px;
  }
  #given-name input{
    height: 15px;
    width: 150px;
    border-radius: 5px;
    padding: 10px;
    font-size: 14px;
    border: 1px solid #ccc;
  }
  #given-name input:focus{
    border: 1px solid steelblue;
    color: steelblue;
    outline: none;
  }
</style>

<template>
  <header>
    <div id="about-user">
      <p>name <span>{{user}}</span></p>
      <p>score:<span v-if="played>0">{{done}} / {{played}}</span></p>
    </div>
    <div id="app-name">
      <h1>Quiz App</h1>
      <div id="given-name">
        <input type="text" v-model.trim.lazy="user" placeholder="Enter your name">
      </div>
    </div>
  </header>
</template>

<script>
import { ref } from 'vue'
export default {
  name: "Header.vue",
  props: {
    done: {
      type: Number,
      default: 2
    },
    played: {
     type: Number,
     default: 6
    }
  },
  setup(){
    const user = ref('nancy')
    return {user}
  }
}
</script>

