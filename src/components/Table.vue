<template>
  <div class="From">
    <el-table :data="props.data">
      <el-table-column
          v-for='(item, index) in cols'
          :key='index'
          :align='item.align'
          :label='item.label'
          :prop='item.prop'
          :type='item.type'
          :width="item.width + 'px'"
      >
        <template v-if='item.slot' v-slot='{ row, $index, column }'>
          <slot
              :column='column'
              :index='$index'
              :name='item.slot'
              :row='row'
          ></slot>
        </template
        >
      </el-table-column>
    </el-table>
  </div>
</template>

<script setup>
import {defineProps} from "vue";

const props = defineProps({
  data: {
    type: Array, // data 表格数据
    default: () => []
  },
  cols: {
    type: Array, // cols 表格列
    default: () => []
  }
})


</script>
<style lang="scss" scoped>

</style>
