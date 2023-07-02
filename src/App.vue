<script>
import ItemList from './components/ItemList.vue'

export default {
  name: 'App',
  components:{
    ItemList
  },

  data(){
    return {
      isStudentListOpen: false
    }
  },
}
</script>

<template>
  <div class="wrapper">
    
    <h1> Список студентов</h1>
    <button @click="isStudentListOpen=!isStudentListOpen" class="btnShow"> 
        <span v-text="isStudentListOpen? 'Закрыть' : 'Показать'"> </span>
        список студентов
    </button>

    <item-list v-if="isStudentListOpen"/>
    
  </div>
</template>

<style>

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 60px;
  word-wrap: break-word;
  width: 100vw;
}

.wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 16px;
}

.btnShow {
  padding: 16px 32px;
  border-radius: 12px;
  color:white;
  background-color: blue;
  font-size: 18px;
  font-weight: 400;
  cursor: pointer;
  transition: background-color 0.3s ease-in;
  border: none;
  width: fit-content;
  display: block;
  min-width: 300px;
}

.btnShow:hover {
  background-color:black;
} 

</style>
