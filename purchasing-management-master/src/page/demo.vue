<template>
  <div>
    <page-header></page-header>
    <el-row>
      <el-col :span="leftV" :style="{height: clientHeight + 'px', overflow: 'auto'}">
        <side-bar :isCollapse="isCollapse" @closeSidebar="closeSidebar"></side-bar>
      </el-col>
      <el-col :span="rightV" :style="{height: clientHeight + 'px', overflow: 'auto'}">
        <router-view></router-view>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      leftV: 4,
      rightV: 20,
      isCollapse: false,
      clientHeight: 100
    };
  },
  mounted() {
    // debugger
    const that = this;
    window.clientHeight = document.body.clientHeight;
    that.clientHeight = Number(window.clientHeight) - 44;
    // window.onresize = () => {
    //   return (() => {
    //     window.clientHeight = document.body.clientHeight;
    //     that.clientHeight = window.clientHeight;
    //   })();
    // };
  },
  methods: {
    closeSidebar() {
      this.isCollapse = !this.isCollapse;
      if (this.isCollapse) {
        this.leftV = 1;
        this.rightV = 23;
      } else {
        this.leftV = 4;
        this.rightV = 20;
      }
    }
  }
};
</script>

<style>
html {
  background: #f1f1f1;
  height: 100%;
}
body {
  margin: 0;
  height: 100%;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0;
  min-width: 1160px;
}
.rightArea {
  background: #fff;
  width: 99%;
  float: right;
  padding-bottom: 20px;
}
.el-radio-button__orig-radio:checked + .el-radio-button__inner {
  background-color: #cb1235 !important;
  border-color: #cb1235 !important;
}
.el-radio-button__inner:hover {
  color: #cb1235;
}
.el-button--default:focus,
.el-button--default:hover {
  color: #606266;
  border-color: #dcdfe6;
  background-color: #fff;
}
.el-button--text {
  color: #1e88e5;
}
.el-button--text:active {
  color: #1e88e5;
}
.el-button--text:hover {
  color: #1e88e5;
  border-color: transparent;
  background-color: transparent;
}
.el-button--primary {
  color: #fff !important;
  background-color: #cb1235 !important;
  border-color: #cb1235 !important;
}
/* .el-input__inner:focus, .el-input__inner:active{
  border-color:  #cb1235!important;
} */

.addgroup .el-form--inline .el-form-item__content{
  width: 76% !important;
}
.block {
  margin-top: 20px;
}

/*form表单表格化 start*/
.base-form {
  border: 1px solid #ccc;
  border-right: 0;
  border-top: 0;
}
.base-form .el-form-item {
  margin-bottom: 0 !important;
}
.base-form .el-form-item__label {
  border: 0;
  border-top: 1px solid #ccc;
}
.base-form .el-form-item__content {
  border: 1px solid #ccc;
  border-bottom: 0;
  padding-left: 10px;
  padding-right: 10px;
  /*text-overflow: ellipsis;*/
  /*white-space: nowrap;*/
}
.base-form .el-date-editor.el-input {
  width: 100%;
}
/*form表单表格化 end*/

.dialogBox .el-dialog__header {
  background: #333;
  padding: 0;
}
.dialogBox .el-dialog__title {
  line-height: 40px;
  color: #fff;
  padding-left: 20px;
}

.dialogBox .el-dialog__headerbtn {
  top: 11px;
}
.dialogBox .block {
  float: left;
}
.dialogBox .el-dialog__body {
  padding-top: 10px;
}
.dialogBox .el-dialog__headerbtn .el-dialog__close {
  color: #fff;
}
.dialogBox .el-dialog__headerbtn:focus .el-dialog__close,
.el-dialog__headerbtn:hover .el-dialog__close {
  color: #fff;
}
.el-button--primary:hover {
  color: #fff !important;
}
.el-tree-node:focus > .el-tree-node__content {
  background: #ffe6b0;
}
.el-tree-node__content:hover {
  background-color: #efefef;
}
/* 列表状态按钮颜色 */

.btnClass {
  width: auto;
  background: none;
  border: 1px solid #dcdfe6;
  color: #606266;
  border-radius: 3px;
  line-height: 1;
  padding: 7px 15px;
  font-size: 12px;
}

.btnClass_bjz {
  background: #a1887f;
  color: #fff;
}
.btnClass_ytg {
  background: #4db6ac;
  color: #fff;
}
.btnClass_yzz {
  background: #f05050;
  color: #fff;
}
.btnClass_spz {
  color: #fff;
  background: #5d9cec;
}
.rightArea h1 {
  float: left;
  margin-top: 10px;
  margin-left: 10px;
  width: 90%;
  font-size: 16px;
  text-align: left;
}
</style>
