<template>
  <div>
    <button type="button" :disabled="disabled" @click="onClick()">{{ text }}</button>
    <button class="reset-button" @click="$emit('global-reset')"> Obriši sve</button>
  </div>
</template>

<script>
  export default {
    name: 'Button',
    props: {
      text: String,
      disabled: Boolean,
      person: String,
      food: Array
    },
    methods: {
      onClick() {
        if (confirm(`${this.person}, želiš li sigurno naručiti ${this.food}?`)) {
          this.$emit('order-placed', this.person, this.food)
        }
      },
    },
    emits: ['global-reset']
  }
</script>

<style scoped>
  div {
    text-align: center;
    margin-top: 20px;
  }
  .reset-button {
    background-color:red;
    border-radius:10px;
    border:1px solid #18ab29;
    display: inline-block;
    cursor:pointer;
    color:#ffffff;
    font-size:15px;
    padding:5px 5px;
    text-decoration:none;
    text-shadow:0px 1px 0px #2f6627;
    float: right;
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
