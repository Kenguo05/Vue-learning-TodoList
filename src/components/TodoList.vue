<template>
    <ul class="MyList">
        <TodoItem v-for="todo in todoList" :key="todo.id" :todo="todo"/>
    </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
    name: 'TodoList',
    props:['todoList'],
    components:{
        TodoItem
    }
}
</script>

<style scoped>
.MyList{
    margin-left: 0px;
    border: 1px solid #ddd;
    border-radius: 2px;
    padding: 0px;
}
.MyList-empty{
    height: 40px;
    line-height: 40px;
    border: 1px;
    border-radius: 2px;
    padding-left: 5px;
    margin-top: 10px;
}
</style>