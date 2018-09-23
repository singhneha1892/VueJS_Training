<template>
    <div class="addTodo">
        <h4> TODO </h4>
        <div>
            <label> 
                Add Todo
            </label>
            <input type="text" v-model="todoItem">
            </input>
        </div>
        <div>
            <button class="addTodoButton btn btn-primary" 
                    @click="handleAddTodo"
                    :disabled="todoList.length >= maxAllowedTodo"> 
                    Add
            </button>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'addTodo',
        props: ['maxAllowedTodo', 'todoList'],
        data() {
            return {
                todoItem: ""
            }
        },
        methods: {
            handleAddTodo() {
                this.$emit('addTodo', this.todoItem);
                this.todoItem = "";
            }
        }
    }
</script>

<style scoped>
    .addTodo{
       margin-right: 20%;
       margin-bottom: 30px;
       padding-left:5%
    }
    button {
        margin-top: 20px;
    }
</style>