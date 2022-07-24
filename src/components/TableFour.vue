<template>
  <div>
    <table class="tl_table">
      <thead>
        <th>得分</th>
        <th>90-110</th>
        <th>75-90</th>
        <th>60-75</th>
        <th>0-60</th>
      </thead>
      <tbody>
        <td>等级</td>
        <td>优秀</td>
        <td>良好</td>
        <td>及格</td>
        <td>不及格</td>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
};
</script>

<style scoped>
.tl_table {
  width: 875px;
  height: 72px;
  border: 1px solid #faac3d;
  border-spacing: 0;
}
.tl_table th,.tl_table td{
    border: 1px solid #faac3d;
    width: 150px;
    text-align: center;

}
.tl_table th {
    height: 36px;
    background-color: #FEDAAB;
    color: #D57040;
}
.tl_table th:nth-child(1){
    color: #57585A;
    background-color: #FFCC4D;
}
.tl_table td {
    height: 36px;
    color: #57585A;
    font-weight: 500;
}
</style>