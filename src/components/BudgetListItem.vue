<template>
  <div>
    <div class="list-item" v-for="(item, prop) in list" :key="prop">
      <span class="budget-comment">{{ item.comment }}</span>
      <span class="budget-value">{{ item.value }}</span>
      <el-button type="danger" size="mini" @click="deleteItem(item.id)"
        >Delete</el-button
      >
    </div>
  </div>
</template>
<script>
export default {
  name: 'BudgetListItem',
  props: {
    list: {
      type: Object,
      default: () => ({}),
    },
  },
  methods: {
    deleteItem(id) {
      this.$emit('deleteItem', id);
    },
  },
};
</script>

<style scoped>
.budget-list-wrap {
  max-width: 600px;
  margin: 0 auto;
}
.list-item {
  display: flex;
  align-items: center;
  padding: 10px 15px;
}
.budget-value {
  font-weight: bold;
  margin-left: auto;
  margin-right: 20px;
}
</style>
