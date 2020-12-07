
<template>
  <div id="app">
 <TodoHeader/>
 <TodoInput v-on:addTodo="addTodo"/>
 <TodoList v-bind:propsdata="todoItems"/>
 <TodoFooter/>

  </div>
 
  
</template>

<script>
import  TodoFooter from './components/TodoFooter.vue'
import  TodoInput from './components/TodoInput.vue'
import  TodoList from './components/TodoList.vue'
import  TodoHeader from './components/TodoHeader.vue'

export default {
  data(){
    return {
      todoItems : []
    }
  },
  methods: {
     addTodo(){
            if(this.newTodoItem !== ''){
                var value=this.newTodoItem && this.newTodoItem.trim();
 localStorage.setItem(value, value)
 this.clearInput();

            }
           
        }, 
  },
  components : {
    'TodoHeader' : TodoHeader,
    'TodoInput' : TodoInput,
    'TodoList' : TodoList,
    'TodoFooter' : TodoFooter
  }
}
</script>
<style>
body {
    text-align:center; background-color:#F6F6F8
}
input {
    border-style : groove;
    width:200px
}
button {
    border-style : grrove;
}
.shadow {
    box-shadow : 5px 10px 10px rgba(0,0,0,0,0.03)
}
</style>