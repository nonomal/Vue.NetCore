<!--
*Author：jxx
 *Contact：283591387@qq.com
 *代码由框架生成,任何更改都可能导致被代码生成器覆盖
 *业务请在@/extension/system/Sys_Log.js此处编写
 -->
<template>
  <view-grid
    ref="grid"
    :columns="columns"
    :detail="detail"
    :editFormFields="editFormFields"
    :editFormOptions="editFormOptions"
    :searchFormFields="searchFormFields"
    :searchFormOptions="searchFormOptions"
    :table="table"
    :extend="extend"
    :delBefore="delBefore"
  >
  </view-grid>
</template>
<script setup>
import extend from "@/extension/sys/system/Sys_Log.js";
import { ref, defineComponent } from "vue";

const delBefore = (rows) => {
  console.log("删除前setup:", rows);
  return true;
};

const table = ref({
  key: "Id",
  footer: "Foots",
  cnName: "系统日志",
  name: "Sys_Log",
  url: "/Sys_Log/",
  sortName: "Id",
});
const editFormFields = ref({});
const editFormOptions = ref([]);
const searchFormFields = ref({
  BeginDate: "",
  Url: "",
  LogType: [],
  Success: [],
  UserIP: "",
  ServiceIP: "",
  Role_Id: "",
});
const searchFormOptions = ref([
  [
    { title: "请求地址", field: "Url", type: "text" },
    { title: "用户IP", field: "UserIP", type: "text" },
    { title: "服务器IP", field: "ServiceIP", type: "text" },
  ],
  [
    { title: "开始时间", field: "BeginDate", type: "datetime" },
    {
      dataKey: "restatus",
      data: [],
      title: "响应状态",
      field: "Success",
      type: "selectList",
    },
    { dataKey: "roles", data: [], title: "角色ID", field: "Role_Id", type: "select" },
  ],
  [
    {
      dataKey: "log",
      data: [],
      title: "日志类型",
      field: "LogType",
      colSize: 12,
      type: "checkbox",
    },
  ],
]);
const columns = ref([
  {
    field: "Id",
    title: "Id",
    type: "int",
    width: 90,
    hidden: true,
    readonly: true,
    require: true,
    align: "left",
  },
  {
    field: "BeginDate",
    title: "开始时间",
    type: "datetime",
    width: 140,
    align: "left",
    sortable: true,
  },
  { field: "UserName", title: "用户名称", type: "string", width: 90, align: "left" },
  { field: "Url", title: "请求地址", type: "string", width: 110, align: "left" },
  {
    field: "LogType",
    title: "日志类型",
    type: "string",
    bind: { key: "log", data: [] },
    width: 80,
    align: "left",
  },
  {
    field: "Success",
    title: "响应状态",
    type: "int",
    bind: { key: "restatus", data: [] },
    width: 80,
    align: "left",
  },
  { field: "ElapsedTime", title: "时长", type: "int", width: 60, align: "left" },
  {
    field: "RequestParameter",
    title: "请求参数",
    type: "string",
    width: 70,
    align: "left",
  },
  {
    field: "ResponseParameter",
    title: "响应参数",
    type: "string",
    width: 70,
    align: "left",
  },
  {
    field: "ExceptionInfo",
    title: "异常信息",
    type: "string",
    width: 70,
    align: "left",
  },
  { field: "UserIP", title: "用户IP", type: "string", width: 90, align: "left" },
  {
    field: "ServiceIP",
    title: "服务器IP",
    type: "string",
    width: 90,
    hidden: true,
    align: "left",
  },
  {
    field: "BrowserType",
    title: "浏览器类型",
    type: "string",
    width: 90,
    align: "left",
  },
  {
    field: "User_Id",
    title: "用户ID",
    type: "int",
    width: 90,
    hidden: true,
    align: "left",
  },
  {
    field: "Role_Id",
    title: "角色ID",
    type: "int",
    bind: { key: "roles", data: [] },
    width: 90,
    hidden: true,
    align: "left",
  },
  {
    field: "EndDate",
    title: "结束时间",
    type: "datetime",
    width: 150,
    hidden: true,
    align: "left",
    sortable: true,
  },
]);
const detail = ref({
  cnName: "#detailCnName",
  columns: [],
  sortName: "",
  key: "",
});
</script>
