<template>
  <div class="Form">
    <ElForm :data="formData"></ElForm>
  </div>
</template>
<script>
import ElForm from "../components/ElForm";
export default {
  name: "Form",
  components: { ElForm },
  data() {
    return {
      formData: {
        width: "100px",
        items: [
          {
            type: "Input",
            label: "活动名称",
            prop: "name",
            width: "220px",
            placeholder: "请输入活动名称",
          },
          {
            type: "Select",
            label: "地区选择",
            prop: "region",
            width: "220px",
            placeholder: "请选择地区选择",
            options: [
              {
                value: "zhengzhou",
                label: "郑州",
              },
              {
                value: "anyang",
                label: "安阳",
              },
            ],
          },
          {
            type: "Switch",
            label: "既时配送",
            prop: "delivery",
          },
          {
            type: "Checkbox",
            label: "兴趣爱好",
            prop: "type",
            options: [
              {
                label: "吃饭",
                value: "吃饭",
              },
              {
                label: "睡觉",
                value: "睡觉",
              },
              {
                label: "打游戏",
                value: "打游戏",
              },
            ],
          },
          {
            type: "Radio",
            label: "特殊资源",
            prop: "resource",
            options: [
              {
                label: "线上授课",
                value: "线上授课",
              },
              {
                label: "线下授课",
                value: "线下授课",
              },
            ],
          },
          {
            type: "Textarea",
            label: "活动形式",
            prop: "desc",
            placeholder: "请填写活动形式",
          },
        ],
      },
    };
  },
  methods: {},
  created() {},
  mounted() {},
};
</script>
<style lang="scss" scoped></style>
