<template>
  <nm-form-dialog ref="form" v-bind="form" v-on="on" :visible.sync="visible_">
    <el-row>
      <el-col :span="20" :offset="1">
        <el-form-item label="扩展名：" prop="ext">
          <el-input v-model="form.model.ext" clearable/>
        </el-form-item>
        <el-form-item label="值：" prop="value">
          <el-input v-model="form.model.value" clearable/>
        </el-form-item>
      </el-col>
    </el-row>
  </nm-form-dialog>
</template>
<script>
import api from '../../../../api/MediaType'
import { mixins } from 'nm-lib-skins'
export default {
  mixins: [mixins.formDialogEdit],
  data() {
    return {
      api,
      form: {
        title: '编辑多媒体',
        width: '40%',
        action: api.update,
        model: {
          ext: '',
          value: ''
        },
        rules: {
          ext: [{ required: true, message: '请输入扩展名' }],
          value: [{ required: true, message: '请输入值' }]
        }
      }
    }
  }
}
</script>
