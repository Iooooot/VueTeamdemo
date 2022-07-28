<template>
  <div class="progress" ref="echarts"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "GradeCategory",
  props: ["score", "operate", "indexTitle", "indexValue", "fullmark"],
  data() {
    return {
      option: {
        grid: {
          top: 0,
          height: 40
        },
        title: {
          text: this.indexTitle,
          textStyle: {
            color: '#ef823d',
            fontSize: '10px'
          },
        },

        xAxis: [
          {
            show: false,
            type: "value",
          },
        ],
        yAxis: [
          {
            show: false,
            type: "category",
          },
        ],
        series: [],
      },
    };
  },
  mounted() {

    //整的有几份
    let index = parseInt(this.score / 5);
    //最后一份余的
    let value = this.score - index * 5;
    //最后一份占比
    let last = value / 5;

    let colors = ["#FFCC4D", "#99D4C4", "#E3D070", "#B0D9A4", "#F4793F"].reverse();
    let partValue = [0, 5, 10, 15, 20];
    let series = [];

    for (let i = 0; i < index; i++) {
      let data = {
        type: "bar",
        stack: "total",
        data: [1],
        barWidth: 5,
        yAxisIndex: 0,
        itemStyle: {
          color: colors[i]
        },
      };
      if (this.operate == "push") {
        this.option.title = {
          text: this.indexTitle,
          left: 18,
          textStyle: {
            color: '#ef823d',
            fontSize: '11px'
          },
        }
        if (this.fullmark == 10) {
          this.option.title.left = 18
        }
        series.push(data);
      }
      if (this.operate == "unshift") {
        this.option.title = {
          text: this.indexTitle,
          right: 18,
          textStyle: {
            color: '#ef823d',
            fontSize: '11px'
          },
        }
        if (this.fullmark == 10) {
          this.option.title.right = 18
        }
        series.unshift(data);
      }
    }

    let data = {
      type: "bar",
      stack: "total",
      data: [last],
      barWidth: 5,
      yAxisIndex: 0,
    };
    if (this.operate == "push") {
      series.push(data);
    }
    if (this.operate == "unshift") {
      series.unshift(data);
    }

    this.option.series = series;
    var myChart = echarts.init(this.$refs.echarts);
    this.$nextTick(() => {
      myChart.resize();
    });
    myChart.setOption(this.option);
  },
};
</script>

<style>
.progress {
  width: 240px;
  height: 40px;
  /*background-color: red;*/
}
</style>