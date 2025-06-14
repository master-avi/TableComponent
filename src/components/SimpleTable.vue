<template>
  <table border="1" cellspacing="0" cellpadding="5">
    <thead>
      <tr>
        <th v-for="column in columns" :key="column.key">
          {{ column.title }}
        </th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, index) in data" :key="index">
        <td v-for="column in columns" :key="column.key">
          <span v-if="column.customRender">
            {{ column.customRender(item[column.key], item) }}
          </span>
          <span v-else>
            {{ item[column.key] }}
          </span>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
defineProps({
  data: {
    type: Array,
    required: true
  },
  columns: {
    type: Array,
    required: true
  }
})
</script>