<script setup>
import { ElButton } from 'element-plus'
const buttons = [
  { type: '', text: '项目名称' },
  { type: 'primary', text: '年份' },
  { type: 'success', text: '合作方' },
]


import { ref } from 'vue'
const textarea = ref('')

const handleClick = (text) => {
  textarea.value += `【${text}】`
}

const handleClear = () => {
  textarea.value = ''
}
</script>

<template>
  <div class="flex flex-col mb-4 gap-4">
    <el-button v-for="button in buttons"
               :key="button.text"
               :type="button.type" text bg
               @click="handleClick(button.text)">
      {{ button.text }}
    </el-button>
    <br>
  </div>


  <el-input
      v-model="textarea"
      :rows="20"
      type="textarea"
      placeholder="Please input"
  />

  <div class="mt-4">
    <el-button type="success" @click="handleSave">保存模板</el-button>
    <el-button @click="handleClear">清空</el-button>
  </div>
</template>
