<template>
    <li class="MyItem">
        <label>
            <input type="checkbox" :checked="todo.done" @change="toggle(todo.id)">
            <span>{{ todo.title }}</span>
        </label>
        <button class="btn btn-danger" @click="remove(todo.id)">delete</button>
    </li> 
</template>

<script>
export default {
    name:'TodoItem',
    props:['todo'],
    methods:{
        toggle(id){
            this.$bus.$emit('check', id)
        },
        remove(id){
            if (confirm('Are you sure to delete?')) {
                this.$bus.$emit('remove', id)
            }
        }
    }
}
</script>

<style scoped>
li {
    list-style: none;
    height: 36px;
    line-height: 36px;
    padding: 0 5px;
    border-bottom: 1px solid #ddd;
}
li label {
    float: left;
    cursor: pointer;
}
li label li input {
    vertical-align: middle;
    margin-right: 6px;
    position: relative;
    top: -1px;
}
li button {
    float: right;
    display: none;
    margin-top: 3px;
}
li:before {
    content: initial;
}
li:last-child {
    border-bottom: none;
}
li:hover {
    background-color: lightgray;
}
li:hover button {
    display: block;
}
</style>