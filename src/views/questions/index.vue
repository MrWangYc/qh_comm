<template>
  <el-table
    :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
    style="width: 100%">
    <el-table-column
      label="题目类型"
      prop="type">
    </el-table-column>
    <el-table-column
      label="题目内容"
      prop="content">
    </el-table-column>
    <el-table-column
      align="right">
      <template slot="header" slot-scope="scope">
        <el-input
          v-model="search"
          size="mini"
          placeholder="输入关键字搜索"/>
      </template>
      <template slot-scope="scope">
        <el-button
          size="mini"
          @click="handleEdit(scope.$index, scope.row)">修改</el-button>
        <el-button
          size="mini"
          type="danger"
          @click="handleDelete(scope.$index, scope.row)">删除</el-button>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
export default {
  name: 'IndexVue',
  data() {
    return {
      tableData: [{
        type: '2016-05-02',
        content: '王小虎'
      }, {
        type: '2016-05-04',
        content: '王小虎'
      }, {
        type: '2016-05-01',
        content: '王小虎'
      }, {
        type: '2016-05-03',
        content: '王小虎'
      }],
      search: ''
    }
  },
  methods: {
    handleEdit(index, row) {
      console.log(index, row)
    },
    handleDelete(index, row) {
      console.log(index, row)
    }
  },
}
</script>

<style scoped>

</style>
