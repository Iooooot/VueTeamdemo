<template>
  <div class="progress" ref="echarts"></div>
</template>

<script>
import * as echarts from "echarts";
export default {
  name: "GradeCategory",
  props: ["score", "operate","indexTitle","indexValue","fullmark"],
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
    
    if(this.fullmark == 10){
      this.score =this.score * 2.5
    }
    let index = parseInt(this.score / 5);
    let value = this.score - index * 5;
    let last = value / 5;

    // let indexValue = ["0~5", "5~10", "10~15", "15~20", "20~25"];
    let colors = ["#FFCC4D","#99D4C4","#E3D070","#B0D9A4","#F4793F"];
    let partValue = [0, 5, 10, 15, 20];
    let series = [];

    for (let i = 0; i < index; i++) {
      let data = {
        type: "bar",
        stack: "total",
        data: [1],
        barWidth: 5,
        yAxisIndex: 0,
        itemStyle: colors[i],
        label: {
          show: true,
          color: "black",
          fontSize: 10,
          position: "bottom",
          formatter: this.indexValue[i],
        },
      };
      if (this.operate == "push") {
        this.option.title={
          text: this.indexTitle,
          left:15,
          textStyle: {
            color: '#ef823d',
            fontSize: '10px'
          },
        }
        if(this.fullmark == 10){
          this.option.title.left = 20
        }
        series.push(data);
      }
      if (this.operate == "unshift") {
        this.option.title={
          text: this.indexTitle,
          right:30,
          textStyle: {
            color: '#ef823d',
            fontSize: '11px'
          },
        }
        if(this.fullmark == 10){
          this.option.title.right = 40
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
      label: {
        show: true,
        color: "#F19253",
        fontSize: 10,
        position: "top",
        formatter: params =>{
          if(this.fullmark == 10){
            return (parseFloat(this.score) / 2.5)
          }
          return this.score
        } 
      },
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