<template>
  <el-table
    :data="unitEngineeringTableData"
    border
    stripe
    tooltip-effect="dark"
    style="width:63%"
    highlight-current-row
    @selection-change="handleSelectionChange">
    <el-table-column
      type="selection"
      width="55" align="center">
    </el-table-column>
    <el-table-column
      label="工程名称"
      prop="name"
      width="200"
      show-overflow-tooltip
      align="center">
    </el-table-column>
    <el-table-column
      label="工程类别"
      width="200"
      prop="engineeringCategory"
      show-overflow-tooltip
      align="center">
    </el-table-column>
  </el-table>
</template>
<script>
  export default{
    data(){
      return{
        selectedRows:[],
      }
    },
    props:['unitEngineeringTableData'],
    methods:{
      handleSelectionChange(selectedRows){
        this.selectedRows = selectedRows
        this.$emit('handleSelectionChange',this.selectedRows)
      }
    }
  }
</script>
