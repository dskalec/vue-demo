<template>
  <div v-for="order in orders" :key="order.id">
    <Order :order="order" />
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
    }
  }
</script>

<style>

</style>