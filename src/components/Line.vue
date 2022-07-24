<template>
  <div class="line">折线图</div>
</template>

<script>
import * as echarts from "echarts";
export default {
    props:["test"],
    data() {
    
    return {
      option: {
        title: {
          text: "", //标题
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "cross",
            label: {
              backgroundColor: "#6a7985",
            },
          },
        },
        legend: {
          right: "auto",
          itemWidth: 40,
          itemGap: 50,
          data: ["学生得分", "班级平均分"],
        },
        grid: {
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true,
        },
        xAxis: [
          {
            type: "category",
            axisTick: {
              show: false, // 去除刻度线
            },
            axisLabel: {
              //文本样式
              fontSize: "9",
              color: "#535354",
              margin: 10,
            },
            axisLine: {
              symbolSize:[15,15],
              show: true, // x轴线
              lineStyle: {
                // x轴样式
                color: "#F08744",
                width: "1",
                //利用阴影进行延长
                shadowOffsetX: 20, //
                shadowColor: "#F08744",
              },
            },
            // boundaryGap: false,
            data: ["美术表现", "文化理解", "图像识读", "创新实践", "审美判断"],
          },
        ],
        yAxis: [
          {
            type: "value",

            axisLabel: {
              //文本样式
              fontSize: "10",
              color: "#535354",
              formatter: function (value) {
                return value.toFixed(2);
              },
            },

            splitLine: {
              //y轴分割线
              lineStyle: {
                // 设置背景横线
                color: "#F08744",
              },
            },

            axisLine: {
              show: true, // y轴线
              lineStyle: {
                // y轴样式
                color: "#F08744",
                width: "1",
                 //利用阴影进行延长
                shadowOffsetY: -30, //
                shadowColor: "#F08744",
              },
            },
          },
        ],
        series: [
          {
            name: "学生得分",
            type: "line",
            color: "#E5C670",
            symbol: "circle",
            symbolSize: 6,
            label: {
              show: true,
              color: "#F08744",
              fontSize: "8",
              // position: "top",
              formatter: function (params) {
                return params.value.toFixed(2);
              },
            },
            lineStyle: {
              //设置折线宽度
              width: 1,
            },
            data: [18.24, 15.58, 24.75, 8.0, 8.0],
          },
          {
            name: "班级平均分",
            type: "line",
            color: "#99D4C4",
            symbol: "circle",
            symbolSize: 6,
            label: {
              show: true,
              color: "#F08744",
              fontSize: "8",
              // position: "bottom",
              formatter: function (params) {
                return params.value.toFixed(2);
              },
            },
            lineStyle: {
              width: 1,
            },
            data: [24.0, 16.0, 24.0, 3.89, 7.86],
          },
        ],
      },
    };
  },
  created() {
    console.log(this.test)
  },
  mounted() {
    console.log(this.test)
    this.option.series[0].data = this.test[0]
   
    this.option.series[1].data = this.test[1]
    var myChart = echarts.init(document.querySelector(".line"));
    myChart.setOption(this.option);
  },
};
</script>

<style>
.line {
  width: 300px;
  height: 180px;
}
</style>