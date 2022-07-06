<template>
  <div id="app">
    <div class="todo-container">
      <div class="todo-wrap">
        <TodoHeader :recieve="recieve"/>
        <TodoList :todoList="todo" :check="check" :remove="remove"/>
        <TodoFooter/>
      </div>
    </div>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'
export default {
  name: 'App',
  data(){
    return {
      todo:[

      ]
    }
  },
  methods:{
    recieve(todo){
      this.todo.unshift(todo)
    },
    check(id){
      this.todo.forEach((t)=>{
        if (t.id === id) {
          t.done = !t.done
        }
      })
    },
    remove(id){
      this.todo = this.todo.filter((t)=>{
        return t.id !== id
      })
    }
  },
  components: {
    TodoHeader,
    TodoList,
    TodoFooter
  }
}
</script>

<style>
.btn {
  display: inline-block;
  padding: 4px 12px;
  margin-bottom: 0;
  font-size: 14px;
  line-height: 20px;
  text-align: center;
  vertical-align: middle;
  cursor: pointer;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.2), 0 1px 2px rgba(0, 0, 0, 0.05);
  border-radius: 4px;
}

.btn-danger {
  color: #fff;
  background-color: #da4f49;
  border: 1px solid #bd362f;
}

.btn-danger:hover {
  color: #fff;
  background-color: #bd362f;
}

.btn:focus {
  outline: none;
}

.todo-container {
  width: 600px;
  margin: 0 auto;
}

.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>
