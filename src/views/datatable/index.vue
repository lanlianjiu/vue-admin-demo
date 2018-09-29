<template>
  <el-table :data="tableData3" height="250" border style="width: 100%">
    <el-table-column prop="date" label="日期" width="180"></el-table-column>
    <el-table-column prop="name" label="姓名" width="180"></el-table-column>
    <el-table-column prop="address" label="地址"></el-table-column>
  </el-table>
</template>

<script>
import http from "../../utils/http";
export default {
  data() {
    return {
      tableData3: []
    };
  },
  created() {
    this.getTablelist();
  },
  methods: {
    getTablelist: function() {
      let data = {
        username: "admin",
        password: 123456
      };
      let that = this;
      http({
        url: "/admin/user/login",
        method: "post",
        data
      })
        .then(function(res) {
          console.log(res);
          that.tableData3 = [
            {
              date: "2016-05-03",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            },
            {
              date: "2016-05-02",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            },
            {
              date: "2016-05-04",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            },
            {
              date: "2016-05-01",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            },
            {
              date: "2016-05-08",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            },
            {
              date: "2016-05-06",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            },
            {
              date: "2016-05-07",
              name: "王小虎",
              address: "上海市普陀区金沙江路 1518 弄"
            }
          ];
        })
        .catch(function(res) {
          console.log(res);
        });
    }
  }
};
</script>

<style lang="stylus" scoped>
</style>
