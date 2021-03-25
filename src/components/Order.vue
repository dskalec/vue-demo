<template>
  <div class="order">
    <h3>{{ order.name }}</h3>
    <template v-for="food in order.food" :key="food">
      <span class="order-food">{{ food }}</span>
    </template>
    <p class="order-time">
      Vrijeme narudžbe: {{order.orderTime}}
      <i class="fas fa-times" @click="deleteOrder(order.id)"></i>
    </p>

  </div>
</template>

<script>
  export default {
    name: 'Order',
    props: {
      order: Object
    },
    methods: {
      deleteOrder(orderId) {
        this.$emit('delete-order', orderId);
      }
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
.order-time {
  float: right;
  font-size: 15px;
  color: #2f6627;
}
.fas {
  color: red;
  padding: 5px 5px;
}
</style>