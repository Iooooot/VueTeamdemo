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
          <td rowspan="2" v-if="index % 2 == 0" class="first">{{ value.id }}</td>
          <td class="second">{{ value.name }}</td>
          <td>{{ value.amount1 }}</td>
          <td class="four">{{ value.amount2 }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
   data() {
    return {
      tableData: [
        {
          id: "基础指标",
          name: "基础知识",
          amount1: "音乐、美术等艺术课程学习的出勤率、参与度和学习任务完成情况",
          amount2: "25",
        },
        {
          id: "基础指标",
          name: "课外活动",
          amount1: "参加学校组织的艺术兴趣小组、艺术社团和各类艺术活动的表现",
          amount2: "15",
        },
        {
          id: "基础指标",
          name: "基础知识",
          amount1: "理解和掌握音乐、美术等艺术课程标准要求的基础知识的情况",
          amount2: "25",
        },
        {
          id: "基础指标",
          name: "基本技能",
          amount1: "掌握和运用音乐、美术等艺术课程标准要求的基本技能的情况",
          amount2: "25",
        },
        {
          id: "基础指标",
          name: "在校学习",
          amount1:
            "自主参加校外艺术学习、参与艺术实践的情况" +
            "(主要指参与社区、乡村文化艺术活动，学习优秀的民族民间艺术，欣赏高雅的文艺演出和展览等)",
          amount2: "10",
        },
        {
          id: "基础指标",
          name: "艺术特长（加分项）",
          amount1:
            "某一艺术项目的特长\n(包括声乐、器乐、舞蹈、戏剧、戏曲、绘画、书法等)",
          amount2: "10",
        },
      ],
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