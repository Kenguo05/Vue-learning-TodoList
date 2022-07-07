<template>
  <div class="MyFooter">
    <label>
        <input type="checkbox">
    </label>
    <span>
        <span>Completed {{ numOfCompleted }}</span> / {{ numOfAll }}
    </span>
    <button class="btn btn-danger" @click="clearAll">Clear all Completed</button>
  </div>
</template>

<script>
export default {
    name:'TodoFooter',
    props:['numOfCompleted','numOfAll','clear'],
    methods:{
        clearAll(){
            this.clear()
        }
    }
}
</script>

<style>
.MyFooter {
    height: 40px;
    line-height: 40px;
    padding-left: 6px;
    margin-top: 5px;
}

.MyFooter label {
    display: inline-block;
    margin-right: 20px;
    cursor: pointer;
}

.MyFooter label input {
    position: relative;
    top: -1px;
    vertical-align: middle;
    margin-right: 5px;
}

.MyFooter button {
    float: right;
    margin-top: 5px;
}
</style>