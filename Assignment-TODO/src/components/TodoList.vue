<template>
    <div class="todoListClass">
        <h4>TODO LIST <span></span></h4>
        <span>Remove the item after task completion</span>
        <div>
            <ol>
                <li v-for="(todoItem, index) of todoList"
                    v-bind:key="index"
                    style="border: 1px solid gray; width: 100px;height: 22px;margin-bottom:10px"
                    >
                    {{ todoItem }}
                    <button class="btn" style="float:right" @click="handleDeleteTodo(index)" :title="todoItem"><i class="fa fa-close">X</i></button>
                </li>
            </ol>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'TodoList',
        props: ['todoList'],
        methods: {
            handleDeleteTodo(index) {
                this.todoList.splice(index, 1);
                this.$emit('todoList', this.todoList);
            }
        }
    }
</script>

<style scoped>
    .todoListClass {
        border: 1px solid gray;
        width: 50%;
        margin-right: 20%;
        padding-bottom: 40px;
        padding-left:5%
    }
</style>