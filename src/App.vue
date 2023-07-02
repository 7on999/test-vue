<script>
import ItemList from './components/ItemList.vue'

export default {
  name: 'App',
  components:{
    ItemList
  },

  data(){
    return {
      isStudentListOpen: false,
      data: [
        {
          name: 'Alex',
          descriotion: 'Трудолюбивый, ответственный, средний балл 4.2',
        },
        {
          name: 'Mark',
          descriotion: 'В течение практики проявил отличные знания в области коммерческой деятельности.',
        },
        {
          name: 'Kirill',
          descriotion: 'Good guy',
        },
        {
          name: 'Alexandr',
          descriotion: 'Силен в естественных науках',
        },
        {
          name: 'Denis',
          descriotion: 'Слаб в математике',
        },
        {
          name: 'Artyom',
          descriotion: 'Слаб в истории',
        },
        {
          name: 'Semyon',
          descriotion: 'Плохая дисциплина',
        },
        {
          name: 'Sergey',
          descriotion: 'Good at everything',
        },
        {
          name: 'Ann',
          descriotion: 'Good guy',
        },
        {
          name: 'Martin',
          descriotion: 'Good at biology',
        },
        {
          name: 'Alexey',
          descriotion: 'Good at Science',
        },
        {
          name: 'Bgor',
          descriotion: 'Good at Math',
        },
        {
          name: 'Egor',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Marina',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Maria',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Student 9',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Student 5',
          descriotion: 'Good at Chemistry',
        },   {
          name: 'Student 6',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Student 7',
          descriotion: 'Good at Chemistry',
        },   {
          name: 'Student 8',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Student 3',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Student 2',
          descriotion: 'Good at Chemistry',
        },
        {
          name: 'Student 1',
          descriotion: 'Good at History',
        }
      ],
    }
  },
  methods: {
    changeDescription({newDescription, studentName}){
      const studentForUpdate = this.data.find(student=>student.name===studentName);
      studentForUpdate.descriotion = newDescription
    },
  }
}
</script>

<template>
  <div class="wrapper">
    
    <h1> Список студентов</h1>
    <button @click="isStudentListOpen=!isStudentListOpen" class="btnShow"> 
        <span v-text="isStudentListOpen? 'Закрыть' : 'Показать'"> </span>
        список студентов
    </button>

    <item-list 
      v-if="isStudentListOpen" 
      :data="data"
      @changeDescriptionStudent='changeDescription'
    />
    
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
