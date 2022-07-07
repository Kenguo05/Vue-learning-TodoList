<template>
    <div class="MyHeader">
      <input type="text" placeholder="www" @keydown.enter="add">
    </div>
</template>

<script>
import {nanoid} from 'nanoid'
export default {
    name:'TodoHeader',
    methods:{
        add(event){
            const todo = {
                id: nanoid(),
                title: event.target.value,
                done: false
            }
            this.recieve(todo)
            event.target.value = ''
        }
    },
    props:['recieve']
}
</script>

<style scoped>
.MyHeader input {
    width: 560px;
    height: 28px;
    font-size: 14px;
    border: 1px solid #ccc;
    border-radius: 4px;
    padding: 4px 7px;
}

.MyHeader input {
    outline: none;
    border-color: rgba(82, 168, 236, 0.8);
    box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(82, 168, 236, 0.8)
}
</style>