<template>
  <div class="progress" ref="echarts"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  data() {
    return {
      option: {
        grid: {
          top: 0,
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
        series: [
          {
            type: "bar",
            stack: "total",
            data: [1],
            barWidth: 5,
            yAxisIndex: 0,
            label: {
              show: true,
              color: "black",
              fontSize: 14,
              position: "bottom",
              formatter: function (params) {
                return "0~5";
              },
            },
            itemStyle: {
              color: "#FFCC4D",
            },
          },
          {
            type: "bar",
            stack: "total",
            data: [1],
            barWidth: 5,
            yAxisIndex: 0,
            label: {
              show: true,
              color: "black",
              fontSize: 14,
              position: "bottom",
              formatter: function (params) {
                return "5~10";
              },
            },
            itemStyle: {
              color: "#99D4C4",
            },
          },
          {
            type: "bar",
            stack: "total",
            data: [1],
            barWidth: 5,
            yAxisIndex: 0,
            label: {
              show: true,
              color: "black",
              fontSize: 14,
              position: "bottom",
              formatter: function (params) {
                return "10~15";
              },
            },
            itemStyle: {
              color: "#E3D070",
            },
          },
          {
            type: "bar",
            stack: "total",
            data: [1],
            barWidth: 5,
            yAxisIndex: 0,
            label: {
              show: true,
              color: "black",
              fontSize: 14,
              position: "bottom",
              formatter: function (params) {
                return "15~20";
              },
            },
            itemStyle: {
              color: "#B0D9A4",
            },
          },
          {
            type: "bar",
            stack: "total",
            data: [1],
            barWidth: 5,
            yAxisIndex: 0,
            label: {
              show: true,
              color: "black",
              fontSize: 14,
              position: "bottom",
              formatter: function (params) {
                return "20~25";
              },
            },
            itemStyle: {
              color: "#F4793F",
            },
          },
        ],
      },
    }
  },
  mounted() {
    var myChart = echarts.init(this.$refs.echarts);
    this.$nextTick(() => {
      myChart.resize();
    });
    myChart.setOption(this.option);
  },
}
</script>

<style>
.progress {
  width: 400px;
  height: 100px;
}
</style>