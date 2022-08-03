<template>
  <div>
    <el-form :model="ruleForm" ref="ruleForm" :label-width="data.width">
      <el-form-item
        v-for="(item, index) in data.items"
        :key="index"
        :label="item.label"
        :prop="item.prop"
      >
        <!-- 输入框部分 -->
        <el-input
          v-model="ruleForm[item.prop]"
          v-if="item.type === 'Input'"
          :style="{ width: item.width }"
          placeholder="请输入内容"
        ></el-input>
        <!-- 下拉框部分 -->
        <el-select
          v-model="ruleForm[item.prop]"
          :placeholder="item.placeholder"
          v-if="item.type === 'Select'"
        >
          <el-option
            :label="Seitem.label"
            :value="Seitem.value"
            v-for="(Seitem, index) in item.options"
            :key="index"
          ></el-option>
        </el-select>
        <!-- swich开关 -->
        <el-switch
          v-model="ruleForm[item.prop]"
          v-if="item.type === 'Switch'"
        ></el-switch>
        <!-- 复选框选择 -->
        <el-checkbox-group
          v-model="ruleForm[item.prop]"
          v-if="item.type === 'Checkbox'"
        >
          <el-checkbox
            v-for="(cheItem, index) in item.options"
            :key="index"
            :label="cheItem.value"
          >
            {{ cheItem.label }}</el-checkbox
          >
        </el-checkbox-group>
        <!-- 单选框部分 -->
        <el-radio-group
          v-model="ruleForm[item.prop]"
          v-if="item.type === 'Radio'"
        >
          <el-radio
            v-for="(RaItem, index) in item.options"
            :key="index"
            :label="RaItem.label"
          ></el-radio>
        </el-radio-group>
        <!-- 文本域部分-->
        <el-input
          type="textarea"
          :placeholder="item.placeholder"
          v-model="ruleForm[item.prop]"
          v-if="item.type === 'Textarea'"
        ></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary">取消</el-button>
        <el-button type="success">确定</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>
<script>
export default {
  props: {
    data: {
      type: Object,
      default: () => {},
    },
  },

  data() {
    return {
      ruleForm: {
        type: [],
      },
    };
  },
  methods: {},
  created() {},
  mounted() {},
};
</script>
<style lang="scss" scoped></style>
