<template>
  <div id="app" class="container">
    <div class="row">
      <addTodo :maxAllowedTodo="maxAllowedTodo" :todoList="todoList" @addTodo="addTodo" /> 
      <div v-if="todoList.length >= maxAllowedTodo" class="warning">
                You cannot add more than {{maxAllowedTodo}} items. 
                <br />
                you need to delete some items to add further todos.
     </div>
     
      <TodoList :todoList="todoList"/>
      <div class="col-xs-3 progressBarStyles">
        <h4> Progress: ({{todos}}/{{maxAllowedTodo}})</h4>
        <div class="progress" style="width: 360px; height: 30px; border:1px solid gray">
        <div :style="progressWidth()"></div>
        </div>
        </div>
    </div>

  </div>
</template>

<script>
import addTodo from './components/addTodo';
import TodoList from './components/TodoList';
export default {
  name: 'App',
  components: {
    addTodo,
    TodoList,
  },
  data() {
    return {
      maxAllowedTodo: 12,
      todoList: [],
   }
  },
  computed: {
    getPercentage() {
      return (this.todoList.length / this.maxAllowedTodo ) * 100;
    },
	todos() {
      return this.todoList.length;
    }
  },
  methods: {
    addTodo(todoItem) {
      this.todoList.push(todoItem);
    },
    progressWidth: function(){
            return {
                'width': (this.todoList.length / this.maxAllowedTodo ) * 100 + '%',
                'background-color': 'red',
                'height': '30'+ 'px'
            };
    }
  }
}
</script>

<style>
.progressBarStyles{
   margin-right: 20%;
   padding-left:5%
}

.warning{
    margin-bottom:20px;
    padding-left:5%;
    color: red
}

  </style>