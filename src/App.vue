<template>
  <SimpleTable :columns="columns" :data="tableData" />
</template>

<script setup>
import { ref } from 'vue'
import SimpleTable from './components/SimpleTable.vue'

const tableData = ref([
  {
    name: 'momiqvoy',
    age: 312,
    address: 'moskva',
    tags: ['nice', 'programmist']
  },
  {
    name: 'baroqvoy',
    age: 2312,
    address: 'doma sidit',
    tags: ['mushukcha']
  },
  {
    name: 'sherlokvatson',
    age: 11,
    address: 'baker strit',
    tags: ['nice', 'tutor']
  }
])

const columns = ref([
  { title: 'Name', key: 'name' },
  { title: 'Age', key: 'age' },
  { title: 'Address', key: 'address' },
  {
    title: 'Tags',
    key: 'tags',
    customRender: (value) => value.join(', ')
  }
])
</script>