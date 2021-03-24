<template>
  <div>
    <button :disabled="disabled">{{ text }}</button>
  </div>
</template>

<script>
  export default {
    name: 'Button',
    props: ['text', 'disabled']  // define props as an array
  }
</script>

<style scoped>
  div {
    text-align: center;
    margin-top: 20px;
  }
  button {
    background-color:#44c767;
    border-radius:28px;
    border:1px solid #18ab29;
    display: inline-block;
    cursor:pointer;
    color:#ffffff;
    font-size:17px;
    padding:16px 31px;
    text-decoration:none;
    text-shadow:0px 1px 0px #2f6627;
  }
  button[disabled]{
    border: 1px solid #999999;
    background-color: #cccccc;
    color: #666666;
    cursor: auto;
  }


</style>
