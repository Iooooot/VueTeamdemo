<template>
  <div>
    <div id="test" style="width:570px;height: 200px;"></div>
  </div>
</template>

<script>
import * as echarts from "echarts";

export default {
  name: "MyTest",
  props: ["value","chartColor"],
  data() {
    return {
      hackReset: false,
      option: {
        grid: {
          width: 400,
          left: 100,
          top:0
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            // 坐标轴指示器，坐标轴触发有效
            type: "shadow", // 默认为直线，可选为：'line' | 'shadow'
          },
        },
        yAxis: {
          data: [
            "课外活动（15分）",
            "参与度（15分）",
            "完成度（5分）",
            "出勤（5分）",
          ],
          type: "category",
          axisLine: {
            lineStyle: {
              color: "orange",
              width: 1, //这里是为了突出显示加上的
            },
          },
          axisTick: {
            show: false,
          },
          axisLabel: {
            show: true,
            textStyle: {
              color: "black", //更改坐标轴文字颜色
              fontSize: 10, //更改坐标轴文字大小
            },
          },
        },
        xAxis: {
          position: "bottom",
          shoe: true,
          type: "value",
          min: 90,
          max: 100,
          axisTick: {
            show: false,
          },
          splitLine: {
            lineStyle: {
              // 使用深浅的间隔色
              color: ["orange"],
              width: 0.5,
            },
          },
          axisLabel: {
            show: true,
            textStyle: {
              color: "black", //更改坐标轴文字颜色
              fontSize: 10, //更改坐标轴文字大小
            },
            formatter: function (value, index) {
              return value + "%";
            },
          },
          axisLine: {
            show: true,
            lineStyle: {
              color: "orange",
              width: 1, //这里是为了突出显示加上的
              shadowOffsetX: 20,
              shadowColor: "orange",
            },
          },
        },
        series: [
          {
            type: "bar",
            stack: "业务",
            barWidth: 10, //柱图宽度
            itemStyle: {
              normal: {
                color: function (params) {
                  var colorList = [
                    "RGB(266,215,198)",
                    "#B5C334",
                    "#FCCE10",
                    "#E87C25",
                  ];
                  return colorList[params.dataIndex];
                },
                label: {
                  show: true,
                  position: "right",
                  formatter: "{c}%",
                  color: "orange",
                },
              },
            },
            data: [
              
            ],
          },
        ],
      },
    };
  },
  methods: {
    // init() {
    //   console.log(chartDom);
    // },
  },
  mounted() {
    this.option.series[0].data = this.value;
    this.option.series[0].itemStyle.normal.color = (params) => this.chartColor[ params.dataIndex]
    let chartDom = document.getElementById("test");
    let myChart = echarts.init(chartDom);
    myChart.setOption(this.option, true);
  },
  watch: {
    value: {
      immediate: true,
      handler(newValue) {
        console.log(newValue);
        // this.init();
      },
    },
  },
};
</script>

<style>
</style>