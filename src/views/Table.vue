<template>
  <div class="Table">
    <ElTable ref="ElTable" :tableData="tableData" :cols="cols">
      <template v-slot:lin="{ row, index }">
        <el-button @click="handleEdit(row)" type="primary" size="small"
          >编辑</el-button
        >
        <el-button @click="handleDel(index)" type="danger" size="small"
          >删除</el-button
        >
      </template>
    </ElTable>
  </div>
</template>
<script>
import ElTable from "../components/ElTable";
export default {
  components: { ElTable },
  data() {
    return {
      tableData: [
        {
          name: "林凯丰",
          Address: "河南省安阳市",
          age: "19",
          day: "2003-07-18",
          occupation: "前端开发",
        },
        {
          name: "林政辉",
          Address: "河南省安阳市",
          age: "19",
          day: "2003-07-18",
          occupation: "小卡辣米",
        },
      ],
      cols: [
        {
          type: "index",
          label: "序号",
          width: "220px",
          align: "center",
        },
        {
          prop: "name",
          label: "名字",
          width: "220px",
          align: "center",
        },
        {
          prop: "Address",
          label: "地址",
          width: "220px",
          align: "center",
        },
        {
          prop: "age",
          label: "年龄",
          width: "220px",
          align: "center",
        },
        {
          prop: "day",
          label: "出生月份",
          width: "220px",
          align: "center",
        },
        {
          prop: "occupation",
          label: "职业",
          width: "220px",
          align: "center",
        },
        {
          label: "操作",
          align: "center",
          slot: "lin",
        },
      ],
    };
  },
  methods: {
    handleEdit(row) {
      console.log(row);
    },
    handleDel(index) {
      const data = this.$refs.ElTable.tableData;
      data.splice(index, 1);
    },
  },
  created() {},
  mounted() {},
};
</script>
<style lang="scss" scoped></style>
