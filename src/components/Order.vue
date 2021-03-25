<template>
  <div class="order">
    <h3>{{ order.name }}</h3>
    <template v-for="food in order.food" :key="food">
      <span class="order-food">{{ food }}</span>
    </template>
  </div>
</template>

<script>
  export default {
    name: 'Order',
    props: {
      order: Object
    }
  }
</script>

<style>
.order {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}
.order-food {
  margin-right: 10px;
  padding: 5px 5px;
}
</style>