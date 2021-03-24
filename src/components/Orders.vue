<template>
  <div>
    <Order />
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