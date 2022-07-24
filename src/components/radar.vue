<template>
    <div>
        <div class="rader" style="width: 240px;height:190px" />
    </div>
</template>

<script>
import * as echarts from "echarts";
export default {
    data() {
        return {
            index: 0,
            // 定义各个维度的最大值
            dataMax:[
                    {
                        name: '美术表现', max: 100
                    },
                    {
                        name: '审美判读', max: 100
                    },
                    {
                        name: '创意实践', max: 100
                    },
                    {
                        name: '图像识读', max: 100
                    },
                    {
                        name: '文化理解', max: 100
                    }
                ],
            datalist:[90,50,60,60,70],
            option: {
                grid: {
                    left: 0,
                    top: 0
                },
                radar: {
                    shape: 'circle',//配置雷达图最外层的图形circle、polygon
                    //配置各个维度的最大值和名称，name，max
                    radius: 57,//缩放,
                    center: ['50%', '50%'],//位置
                    indicator: [
                        {name: '美术表现', max: 100},
                        {name: '审美判读', max: 100},
                        {name: '创意实践', max: 100},
                        {name: '图像识读', max: 100},
                        {name: '文化理解', max: 100}
                    ],
                    //配置雷达图的每一圈的网格线样式
                    splitLine: {     
                        lineStyle: {
                            color: '#a5a5a6',
                            // type: 'dashed',
                            // dashOffset: 20
                            type: [10, 5],
                            dashOffset: 5
                        },
                    },
                    // 雷达图每个指示器名称的配置项
                    axisName:{
                        show:true,//默认也是true
                        color: '#f6b786',
                    },
                    //配置雷达图的射线样式颜色
                    axisLine:{
                        lineStyle: {
                            color: '#f6b786',
                            type: 'dashed',
                            length:30
                        },
                    },

                },
                series: [
                    {
                        zoom:0.8,
                        type: 'radar',//表示一个雷达图
                        label: {      //设置标签的样式
                            show: true,//显示数值
                            color: '#f6b786',
                            formatter: "{c}%"
                        },
                        //设置阴影区域样式
                        itemStyle:{
                            color: '#bcdca4',
                            borderColor: '#bcdca4',
                        },
                        //将每一个产品的雷达形成阴影的面积
                        areaStyle: {
                            color: '#bcdca4',
                        },
                        data: [
                            {
                                name: '学业指标',
                                value: [83.33, 66.67, 66.67, 75, 80],
                            },
                        ],

                    }
                ]
            } 
        }
    },
    methods: {
        
    },
    mounted() {
        var rader = echarts.init(document.querySelector(".rader"));
        rader.setOption(this.option)
    },
}
</script>
