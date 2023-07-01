<script>
import { ref } from 'vue'

export default {
  name: 'ItemList',
  
  updated() {
    const input = document.querySelector('[autofocus]');
    if (input) input.focus()
  },

  data(){
    return {
      selectedPerson: null,
      data: ref([
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
      ]),
    }
  },

  methods: {
    selectPerson(name){
      this.selectedPerson = name;
    },
  }
}
</script>

<template>
  <p> Для изменения описания студентов кликните на соответствующую карточку</p>

  <ul class="ul">
    <li 
      v-for="person in data" 
      :key=person.name

      :class="{
        'defaultListElement':true,
        'activeListElement':person.name===selectedPerson
      }"
      @click="selectPerson(person.name)"
    >
      <span> 
        <span class="bold"> Имя:  </span> 
        {{ person.name }} 
      </span>
      <span v-if="person.name!==selectedPerson">
        <span class="bold"> Характеристика:  </span> 
        {{ person.descriotion }} 
      </span>


      <template v-else>
        <span> Для изменения характеристики введите новое значение в поле для ввода и нажмите клавишу 'enter' </span>
        <span class="descriptiptionSpan"> 
          <span class="bold">Характеристика: </span>
          <input 
            type="text"
            v-model="person.descriotion" 
            @blur="selectedPerson=null" 
            class="input" 
            @keydown.enter="selectedPerson=null"
            autofocus
            />
        </span>
      </template>
    </li>
  </ul>
</template>

<style scoped>
  h3 {
    margin: 40px 0 0;
  }

  .ul {
    display: flex;
    flex-direction: column;
    gap: 16px
  }

   @media (min-width: 580px) { 
    .ul {
      width: 500px;
    }
  } 

  .defaultListElement{
    box-sizing: border-box;
    padding: 16px;
    border: 1px solid blue;
    cursor: pointer;
    display: flex;
    flex-direction: column;
    text-align: start;
    gap:8px;
  }


  .defaultListElement:hover {
  border-color:black
  }

  .activeListElement {
    border-color: green;
  }

  .activeListElement .input{
    outline: none;
    border: 1px solid green
  }

  .descriptiptionSpan{
    display: flex;
    align-items: center;
    gap:16px;
  }

  .input {
    flex-grow: 1;
    padding: 16px;
  }

  .bold {
    color: black;
    font-weight: 600;
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
