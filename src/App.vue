<template>
  <div>
    <div>
      <a-space>
        <a-button @click="fixedAc">1.打开F12调试,设置名称列右边固定</a-button>
        <a-button @click="ellipsisAc">2.设置名称列省略</a-button>
        <a-button @click="setNameNullAc">3.设置第二行名称值为null，打印错误</a-button>
      </a-space>
    </div>

    <div>
      <p>列数据：</p>
      <p>{{ columns }}</p>
      <p>行数据：</p>
      <p>{{ dataSource }}</p>
    </div>

    <a-table :dataSource="dataSource" :columns="columns" rowKey="id"></a-table>
  </div>
</template>

<script setup>
import {ref} from 'vue'

//列
const columns = ref([
  {dataIndex: 'id', title: 'id', width: 200,},
  {dataIndex: 'name', title: 'name', width: 200,},
])
//数据
const dataSource = ref([
  {id: 1, name: '名称1'},
  {id: 2, name: '名称2'},
])

//设置名称右边固定
const fixedAc = () => {
  columns.value[1].fixed = 'right'
}
//设置名称省略
const ellipsisAc = () => {
  columns.value[1].ellipsis = true
}
//设置名称为null
const setNameNullAc = () => {
  dataSource.value[1].name = null
}

</script>
