
<template>
<el-row>
    <el-table
      :data="tableData"
      border
      style="width: 100%">
      <!-- <el-table-column
        label="安装时间"
        width="180">
        <template scope="scope">
          <el-icon name="time"></el-icon>
          <span style="margin-left: 10px">{{ scope.row.date }}</span>
        </template>
      </el-table-column> -->
      <el-table-column
        label="审核编号"
        width="150">
      <template scope="scope">
          {{ scope.row.long }}
      </template>
      </el-table-column>
  	<el-table-column
        label="提交时间"
        width="150">
        <template scope="scope">
          <el-icon name="time"></el-icon>
          <span style="margin-left: 10px">{{ scope.row.date }}</span>
        </template>
      </el-table-column>
      <el-table-column
        label="关键信息（点击查看详情）"
       >
        <template scope="scope">
          <el-popover trigger="hover" placement="top">
            <p>企业名称: {{ scope.row.name }}</p>
            <p>地址: {{ scope.row.address }}</p>
            <div slot="reference" class="name-wrapper">
              <el-tag>{{ scope.row.name }}</el-tag>
            </div>
          </el-popover>
        </template>
      </el-table-column>
    <el-table-column
  	  label="角色"
  	  width="150">
  	  <template scope="scope">
  		<!-- <el-icon name="time"></el-icon> -->
  		<span style="margin-left: 10px">{{ scope.row.role }}</span>
  	  </template>
  	</el-table-column>
  	<el-table-column
  	  label="发布人姓名"
  	  width="150">
  	  <template scope="scope">
  		<!-- <el-icon name="time"></el-icon> -->
  		<span style="margin-left: 10px">{{ scope.row.error }}</span>
  	  </template>
  	</el-table-column>
      <el-table-column label="审核">
        <template scope="scope">
          <el-button
            size="small"
  		  type="success"
            @click="handleEdit(scope.$index, scope.row)">通过</el-button>
          <el-button
            size="small"
            type="danger"
            @click="handleDelete(scope.$index, scope.row)">驳回</el-button>
        </template>
      </el-table-column>
    </el-table>
    <el-table
      :data="tableData2"
      border
      style="width: 100%">
      <!-- <el-table-column
        width="180">
        <template scope="scope">
          <el-icon name="time"></el-icon>
          <span style="margin-left: 10px">{{ scope.row.date }}</span>
        </template>
      </el-table-column> -->
      <el-table-column
        width="150">
      <template scope="scope">
          {{ scope.row.long }}
      </template>
      </el-table-column>
  	<el-table-column
        width="150">
        <template scope="scope">
          <el-icon name="time"></el-icon>
          <span style="margin-left: 10px">{{ scope.row.date }}</span>
        </template>
      </el-table-column>
      <el-table-column
       >
        <template scope="scope">
          <el-popover trigger="hover" placement="top">
            <p>企业名称: {{ scope.row.name }}</p>
            <p>地址: {{ scope.row.address }}</p>
            <div slot="reference" class="name-wrapper">
              <el-tag>{{ scope.row.name }}</el-tag>
            </div>
          </el-popover>
        </template>
      </el-table-column>
          <el-table-column
  	 
  	  width="150">
  	  <template scope="scope">
  		<!-- <el-icon name="time"></el-icon> -->
  		<span style="margin-left: 10px">{{ scope.row.role }}</span>
  	  </template>
  	</el-table-column>
  	<el-table-column
  	  width="150">
  	  <template scope="scope">
  		<!-- <el-icon name="time"></el-icon> -->
  		<span style="margin-left: 10px">{{ scope.row.error }}</span>
  	  </template>
  	</el-table-column>
      <el-table-column >
        <template scope="scope">
            已通过
        </template>
      </el-table-column>
    </el-table>
</el-row>
</template>
<script>
  export default {
    data() {
      return {
        tableData: [{
            long:'20588206',
          date: '2016-05-02',
          name: '需要科目:英语，需要年级：小学二年级',
          role: '家长',
          address: '广西壮族自治区钦州市钦南区',
          error: '张三'
        }, {
            long:'21809798',
          date: '2016-05-04',
          name: '空闲时间：周一上、周五晚',
          role: '学生',
          address: '广西壮族自治区钦州市钦南区',
          error: '李四'
        }, {
            long:'20580001',
          date: '2016-05-01',
          name: '需要科目:语文，需要年级：初中二年级',
          role: '家长',
          address: '广西壮族自治区钦州市钦南区',
          error: '陈某某'
      }],
      tableData2: [{
    long:'20588206',
            date: '2016-05-02',
            name: '空闲时间：周二下、周日晚',
            role: '学生',
            address: '广西壮族自治区钦州市钦南区',
    error: '胡某某'
        }, {
    long:'21809798',
            date: '2016-05-04',
            name: '需要科目:科学，需要年级：小学六年级',
            role: '家长',
            address: '广西壮族自治区钦州市钦南区',
    error: '邵某某'
        }]
      }
    },
    methods: {
      handleEdit(index, row) {
          this.$notify({
            title: '已发送',
            message: '已通知执法人员前往现场处理',
            type: 'success'
          });
      },
      handleDelete(index, row) {
          this.$notify({
  		  title: '已发送',
  		  message: '已向企业联系人发送异常信息',
  		  type: 'success'
  		});
      }
    }
  }
</script>