<template>
  <div>
    <table class="tl_table">
      <thead>
        <th>一级维度</th>
        <th>维度解析</th>
      </thead>

      <tbody>
        <tr v-for="(value, index) in this.tableData" :key="index">
          <td>{{ value.title }}</td>
          <td>{{ value.content }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  props:["tableData"],
  data() {
    return {
    };
  },
};
</script>

<style scoped>
.tl_table {
  width: 875px;
  height: 218px;
  border: 1px solid #faac3d;
  border-spacing: 0;
}
.tl_table th,.tl_table td {
  padding: 6px 16px;
  border: 1px solid #faac3d;
  text-align: center;
}
.tl_table th {
  font-weight: 600;
}
.tl_table th:nth-child(1) {
  width: 275px;
  color: #57585a;
  background-color: #aed8a4;
}
.tl_table th:nth-child(2) {
  width: 600px;
  color: #d57040;
  background-color: #fedaab;
}
.tl_table td:nth-child(1) {
  color: #d57040;
  font-weight: 500;
}
</style>