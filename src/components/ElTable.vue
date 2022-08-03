<template>
  <div>
    <el-table :data="tableData" border style="width: 100%">
      <el-table-column
        v-for="(item, index) in cols"
        :key="index"
        :prop="item.prop"
        :label="item.label"
        :width="item.width"
        :align="item.align"
        :type="item.type"
      >
        <template v-if="item.slot" v-slot="{ row, column, index }">
          <slot
            :row="row"
            :name="item.slot"
            :index="index"
            :column="column"
          ></slot>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>
<script>
export default {
  props: {
    cols: {
      cols: Array,
      default: () => [],
    },
    tableData: {
      tableData: Array,
      default: () => [],
    },
  },
  data() {
    return {};
  },
  methods: {},
  created() {},
  mounted() {},
};
</script>
<style lang="scss" scoped></style>
