<template>
  <div
    class="total-balance"
    :class="{ 'red-balance': total < 0, 'green-balance': total > 0 }"
  >
    Balance: {{ total }}
  </div>
</template>

<script>
export default {
  name: 'TotalBalance',
  props: {
    total: {
      type: Number,
      default: 0,
    },
  },
};
</script>

<style scoped>
.total-balance {
  font-size: 26px;
  text-transform: uppercase;
  padding: 20px;
  text-align: center;
}
.red-balance {
  color: red;
}
.green-balance {
  color: green;
}
</style>
