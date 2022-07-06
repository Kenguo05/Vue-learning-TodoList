<template>
  <div class="MyFooter">
    <label>
        <input type="checkbox">
    </label>
    <span>
        <span>Completed 0</span> / xxx
    </span>
    <button class="btn btn-danger">Clear all</button>
  </div>
</template>

<script>
export default {
    name:'TodoFooter'
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