<template>
  <div class="budget-list-wrap">
    <el-card header="Budget List">
      <!-- <template v-if="!isEmpty"> -->
      <BudgetListItem :list="list" v-if="!isEmpty" @deleteItem="deleteItem" />
      <!-- <div class="list-item" v-for="(item, prop) in list" :key="prop">
          <span class="budget-comment">{{ item.comment }}</span>
          <span class="budget-value">{{ item.value }}</span>
          <el-button type="danger" size="mini" @click="deleteItem(item.id)"
            >Delete</el-button
          >
        </div> -->
      <!-- </template> -->
      <el-alert v-else type="success" title="Done" effect="dark" />
    </el-card>
  </div>
</template>

<script>
import BudgetListItem from '@/components/BudgetListItem';
export default {
  name: 'BudgetList',
  components: {
    BudgetListItem,
  },
  props: {
    list: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    isEmpty() {
      return !Object.keys(this.list).length;
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
/* .list-item {
  display: flex;
  align-items: center;
  padding: 10px 15px;
}
.budget-value {
  font-weight: bold;
  margin-left: auto;
  margin-right: 20px;
} */
</style>
