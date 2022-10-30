<script setup>
// import { ref, computed } from 'vue';

// let id = 0

// const task = ''
// const desc = ''
// const hidecomplete = ref(false)
// const todos= ref ([
//     {id: id++, text: 'Yessir', desc: 'Uhm ok ok1', done:true},
//     {id: id++, text: 'Yeah No', desc: 'Uhm ok ok2',done:false},
//     {id: id++, text: 'Hell No brosky', desc: 'Uhm ok ok3',done:true}
// ])

// const filtered = computed(() => {
//     return hidecomplete.value
//     ? todos.value.filter((t) =>!t.done)
//     : todos.value
// })

// function addtodos(){
//     todos.value.push({
//         id: id++, text: task.value, desc: desc.value, done: false
//     })
//     task.value = ''
//     desc.value = ''
// }


// function removeTodo(todo) {
//   todos.value = todos.value.filter((t) => t !== todo)
// }

import { ref, computed, reactive } from 'vue'

let id = 0

const open = ref(true)

function openthis(){
    open.value = !open.value
}

const newTodo = ref('')
const newTodo2 = ref('')
const hideCompleted = ref(false)
const todos = ref([
  { id: ++id, text: 'Buy milk from the shop', desc:'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam.', done: true },
  { id: ++id, text: 'Learn JavaScript',desc:'sdsd', done: true },
  { id: ++id, text: 'Learn Vue',desc:'sdsd', done: false }
])

// const length = {{todos.length}}

const filteredTodos = computed(() => {
  return hideCompleted.value
    ? todos.value.filter((t) => !t.done)
    : todos.value
})


function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, desc: newTodo2.value, done: false })
  newTodo.value = ''
  newTodo2.value = ''
}
function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}



</script>

<template>
<div class="heads">
    <div class="h All notification" >
        <span>All</span>
        <span class="badge">{{todos.length}}</span>
      </div>
    <div class="h done" @click="hideCompleted = !hideCompleted" >Done</div>
    <div class="h undone" @click="done" >Undone</div>

</div>
<div class="todolistdiv" >
    <ul>
        <li v-for="todo in filteredTodos" :key="todo.id">

          <input type="checkbox" v-model="todo.done">
          <div class="col" >
          <span class="text" :class="{ done: todo.done }">{{ todo.text }}</span>
          <span class="desc" :class="{ done: todo.done }">{{ todo.desc }}</span>
        </div>
          <button  class="del" @click="removeTodo(todo)"></button>
        </li>
      </ul>

      <div class="add" @click="openthis" >

        <svg xmlns="http://www.w3.org/2000/svg" id="Outline" viewBox="0 0 24 24" width="30" height="30"><path d="M23,11H13V1a1,1,0,0,0-1-1h0a1,1,0,0,0-1,1V11H1a1,1,0,0,0-1,1H0a1,1,0,0,0,1,1H11V23a1,1,0,0,0,1,1h0a1,1,0,0,0,1-1V13H23a1,1,0,0,0,1-1h0A1,1,0,0,0,23,11Z"/></svg>

      </div>
      <div v-if="open" class="questions" > 
        <form @submit.prevent="addTodo">
            <input class="in" v-model="newTodo" />
            <br>
            <input class="in" v-model="newTodo2" />
            <button class="plus">Add Todo</button>
          </form>
      </div>
    <!-- <ul>
        <li for="todo in filtered" key="todo.id" >
            <div class="work" >
        <input type="checkbox" v-model="todos.done">
      <span :class="{ done: todos.done }">{{ todos.task }}</span>
      <br>
      <span :class="{ done: todos.done }">{{ todos.desc }}</span>
      <button @click="removeTodo(todo)">X</button>
    </div>
        </li>
    </ul> -->

</div>

</template>
<script>
  // export default{
  //     name: 'child',
  //     props:[todos.length]
  // };
</script>

<style scoped>

    .notification {
        background-color: #555;
        color: white;
        text-decoration: none;
        padding: 15px 26px;
        position: relative;
        display: inline-block;
        border-radius: 2px;
      }

      .notification:hover {
        background: red;
      }

      .notification .badge {
        padding: 5px 10px;
        border-radius: 50%;
        background-color: red;
        color: white;
      }
    a{
        text-decoration: none;
    }

.in{
    width: 100%;
    border: none;
    background-color: #D1DBEE;
    height: 20px;
    border-radius: 5px;
}


    form{
        width: 100%;
        height: fit-content;
        background: #FFFFFF;
        border-radius: 10px;
        margin-bottom: 15px;
        padding: 20px;
        display: flex;
        flex-direction: column;
    }

    .plus{
    border-radius: 8px;
    border: none;
    font-family: 'Inter';
        font-style: normal;
    padding: 0.6em 1.2em;
    font-size: 10px;
    color: #ffffff;
    display: flex;
    align-items: center;
    width: 60px;
    margin-top: 10px;
    font-weight: 500;
    background-color:#008DFF;
    cursor: pointer;
    transition: border-color 0.25s;
  }
 .plus:hover {
    border-color: #646cff;
  }

    .del{
        position: absolute;
    width: 15px;
    height: 15px;
    right: 50px;
    top: 20;
    border-radius: 90px;
    background: #ff0000;
    border: none;

    }

    .text{
        font-family: 'Inter';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 19px;
        text-align: left;
        color: #000000;
    }

    .desc{
        font-family: 'Inter';
font-style: normal;
font-weight: 500;
font-size: 12px;
line-height: 15px;
text-align: left;


color: #808080;
    }
    .add{
        display: flex;
        align-items: center;
        justify-content: center;
        fill: #FFFFFF;
        position: relative;
        filter: drop-shadow(0px 4px 4px rgba(0, 141, 255, 0.43)) drop-shadow(0px 4px 4px rgba(0, 141, 255, 0.43));

width: 60px;
height: 60px;
left: calc(50% - 60px/2 + 134px);
top: calc(50% - 60px/2 + 365.44px);
border-radius: 90px;
background: #008DFF;
    }

    .col{
        display: flex;
        flex-direction: column;
        width: 298px;
height: fit-content;
float: right;
    }

    li{
        width: 100%;
height: fit-content;
background: #FFFFFF;
border-radius: 10px;
margin-bottom: 15px;
padding: 20px;
    }

    ul{
        list-style: none
    }
    .todolistdiv{
        width: 100%;
        height: fit-content;
        text-decoration: none;
    }
    .heads{
        width: 100%;
        height: fit-content;
        display: flex;
        flex-direction: row;
        margin-top: 25px;
        align-items: center;
        justify-content: space-around;
        margin-bottom: 43px;
    }

    .h{overflow: hidden;
        width: fit-content;

height: 40px;
padding: 15px;

background: rgba(0, 141, 255, 0.43);
border-radius: 30px;
        display: flex;
        width: fit-content;
        flex-direction: row;
        align-items: center;
        justify-content: space-around;
        font-family: 'Inter';
font-style: normal;
font-weight: 700;
font-size: 15px;
line-height: 18px;
text-transform: uppercase;

color: #008DFF;
;

    }

</style>