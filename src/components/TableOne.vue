<template>
    <div>
    <table class="tl_table">
      <thead>
        <th>一级指标</th>
        <th>二级指标</th>
        <th>指标内容</th>
        <th>分值</th>
      </thead>

      <tbody>
        <tr v-for="(value, index) in this.tableData" :key="index">
          <td rowspan="2" v-if="index % 2 == 0" class="first">{{ value.title1 }}</td>
          <td class="second">{{ value.title2 }}</td>
          <td>{{ value.content }}</td>
          <td class="four">{{ value.score }}</td>
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
  height: 306px;
  border: 1px solid #FAAC3D;
  border-spacing: 0;
}
.tl_table th,.tl_table td {
  padding: 4px 16px;
  border: 1px solid #FAAC3D;
  text-align: center;
}
.tl_table th {
  font-weight: 600;
}
.tl_table th:nth-child(1),.tl_table th:nth-child(2) {
    color: #57585A;
    background-color: #9AD5C5;
}
.tl_table th:nth-child(1) {
  width: 140px;
}
.tl_table th:nth-child(2) {
  width: 180px;
}
.tl_table th:nth-child(3) {
    width: 500px;
}
.tl_table th:nth-child(4) {
    width: 50px;
}
.tl_table th:nth-child(3),.tl_table th:nth-child(4) {
    color: #D57040;
    background-color: #FEDAAB;
}
.first,.second,.four{
    color: #D67242;
}
</style>