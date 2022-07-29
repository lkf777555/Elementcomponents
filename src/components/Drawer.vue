<template>
  <div class="Drawer">
    <el-drawer v-model="drawer">
      <template #header>
        <h1> {{ title }}</h1>
      </template>
      <template #default>
        <div class="From">
          <slot></slot>
        </div>
      </template>
      <template #footer>
        <div>
          <el-button @click="drawer = false">取消</el-button>
          <el-button type="primary" @click="handleAdd">确定</el-button>
        </div>
      </template>
    </el-drawer>
  </div>
</template>

<script setup>
import {defineProps} from "vue"
import {defineEmits} from "vue";
import {ref} from "vue";

const emits = defineEmits()

const props = defineProps({
  title: { // drawer标题
    type: String,
    default: ""
  }
})

// drawer默认false
const drawer = ref(false)
// 控制drawer显示
const show = () => {
  drawer.value = true
}
// 控制drawer隐藏
const hide = () => {
  drawer.value = false
}
// 向父组件传递一个自定义事件
const handleAdd = () => {
  emits('handleAdd')
}
// 将子组件的属性和方法暴露给父组件的ref获取DOM
defineExpose(
    {
      show,
      hide
    }
)
</script>
<style lang="scss" scoped></style>
