<template>
  <div class="home">
    <Table :cols="cols" :data="data">
      <template v-slot:kai="{row}">
        <el-switch v-model="row.status" @change="handChange(row)"/>
      </template>
      <template v-slot:lin="{row,index,column}">
        <el-button round size="small" type="primary" @click="handleEdit(row)">编辑</el-button>
        <el-button round size="small" type="danger" @click="handleDel(index)">删除</el-button>
      </template>
    </Table>
    <Drawer ref="DrawerEf" title="编辑用户" @handleAdd="handleAdd">
      <Form></Form>
    </Drawer>
  </div>
</template>
<script setup>
import Table from '../components/Table'
import Drawer from '../components/Drawer'
import Form from '../components/Form'
import {reactive} from "vue";
import {ref,} from "vue"

const DrawerEf = ref() //获取到DrawerEf的DOM元素
const cols = [
  {
    type: 'index',
    label: '序号',
    width: '80',
    align: 'center',
  },
  {
    prop: 'name',
    label: '姓名',
    width: '200',
    align: 'center',
  },
  {
    prop: 'age',
    label: '年龄',
    width: '200',
    align: 'center',
  },
  {
    prop: 'day',
    label: '出生年月',
    width: '220',
    align: 'center',
  },
  {
    prop: 'Address',
    label: '家庭地址',
    width: '320',
    align: 'center',
  },
  {
    prop: 'occupation',
    label: '职业',
    width: '200',
    align: 'center',
  },
  {
    label: '状态',
    width: '220',
    slot: 'kai',
    align: 'center',

  },
  {
    label: '操作',
    slot: 'lin',
    width: '220',
    align: 'center',
  }
]
const data = reactive([
  {
    name: '林凯丰',
    age: '19',
    day: '2003年7月18日',
    Address: '河南省安阳市',
    occupation: '前端中级开发',
    status: false,
  },
  {
    name: '王振东',
    age: '19',
    day: '2003年7月18日',
    Address: '河南省安阳市',
    occupation: '前端中级开发',
    status: true,
  },
  {
    name: '陈哲',
    age: 19,
    day: '2003年7月18日',
    Address: '河南鹤壁市',
    occupation: '前端中级开发',
    status: false,
  },
  {
    name: '郭恩',
    age: 22,
    day: '2003年7月18日',
    Address: '河南邯郸',
    occupation: '前端中级开发',
    status: true,
  },
  {
    name: '王志豪',
    age: 22,
    day: '2003年7月18日',
    Address: '河南新乡',
    occupation: '前端中级开发',
    status: false,
  },
  {
    name: 'yangmr',
    age: 22,
    day: '2003年7月18日',
    Address: '河南邯郸',
    occupation: '前端中级开发',
    status: true,
  },
])
const handleDel = (row) => {
  data.splice(row, 1)
  console.log(row)
}
const handleEdit = (row) => {
  DrawerEf.value.show()
  console.log(row)
}
const handChange = (row) => {
  data.status = !row.status
}
const handleAdd = () => {
  DrawerEf.value.hide()
}
</script>
