<template>
  <div v-for="order in orders" :key="order.id">
    <Order @delete-order="$emit('delete-task', order.id)" :order="order" />
  </div>
</template>

<script>
  import Order from "./Order";

  export default {
    name: 'Orders',
    components: {
        Order
    },
    props: {
      orders: Array
    },
    emits: ['delete-task']
  }
</script>

<style>

</style>