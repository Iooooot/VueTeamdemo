<template>
  <div class="container">
    <div class="main">
      <header class="clearfix">
        <!-- 头部logo -->
        <div class="logo">
          <img src="../assets/images/logo.png" alt="logo">
          <span>艺术素质测评云平台</span>
        </div>
        <!-- 头部右侧的图表说明 -->
        <div class="rightExplain clearfix">
          <!-- 说明标签 -->
          <div>
            <span>美术学科艺术素质测评情况</span>
            <img src="../assets/images/radioBk.png" alt="border" />
          </div>
        </div>
        <!-- 头部左侧的学生信息 -->
        <div class="leftStuInfo">
          <div class="NameAndSchool clearfix">
            <span>{{ stuInfo.stuName }}</span>
            <span class="otherInfoTag"><img src="../assets/images/class.png" alt=""><span
                style="letter-spacing:26px;">学</span>校：{{ stuInfo.schoolName }}</span>
          </div>
          <div class="OtherInfo">
            <span class="otherInfoTag"><img src="../assets/images/class.png" alt=""><span
                style="letter-spacing:26px;">班</span>级：{{ stuInfo.stuClass }}</span>
            <span class="otherInfoTag"><img src="../assets/images/grade.png" alt=""><span
                style="letter-spacing:26px;">年</span>级：{{ stuInfo.stuGrade }}</span>
            <span class="otherInfoTag"><img src="../assets/images/level.png" alt=""><span
                style="letter-spacing:26px;">等</span>级：{{ stuInfo.stulevel }}</span>
          </div>
        </div>
      </header>
      <main>
        <div class="clearfix">
          <div class="colorIndex clearfix">
            <span><i :style="{ backgroundColor: chartColors[0] }"></i>课外活动</span>
            <span><i :style="{ backgroundColor: chartColors[1] }"></i>参与度</span>
            <span><i :style="{ backgroundColor: chartColors[2] }"></i>完成度</span>
            <span><i :style="{ backgroundColor: chartColors[3] }"></i>出勤</span>
          </div>

          <echartsCard :cardProp="cardProps[0]" class="clearfix">
            <div class="cardContent">
              <BarChart :value="barChartData" :chartColor="chartColors"></BarChart>
            </div>
            <div class="cardContent textContent" style="width:270px;margin-left: 30px;">
              <img src="../assets/images/littleNav.png">
              <div>
                {{ textInfo[0] }}
              </div>
            </div>
          </echartsCard>
        </div>

        <echartsCard :cardProp="cardProps[1]" class="clearfix">
          <div style="width:590px;height: 300px;" class="cardContent">
            <div class="clearfix">
              <Radar style="float:left" :radarData="radarDatas"></Radar>
              <LineChart :lineChartData="lineChartData" style="float:left"></LineChart>
            </div>
            <div class="indexScore">
              <div class="basicBox">
                <p class="tl_text">基础知识（25分）</p>
                <!-- 基础知识左 -->
                <div class="basicBoxMin">
                  <div class="hid"
                    :style="{ 'width': dynamicWidth[0], 'position': 'absolute', 'direction': 'rtl', 'right': '0' }">
                    <GradeCategory class="tl_step1" :score="25.00" :operate="indexOper[0]" :indexTitle="indexTitle[0]"
                      :indexValue="indexValue[2]"></GradeCategory>
                  </div>
                </div>
                <!-- 基础知识右 -->
                <div class="basicBoxMin">
                  <div class="hid" :style="{ 'width': dynamicWidth[1] }">
                    <GradeCategory :score="25" :operate="indexOper[1]" :indexTitle="indexTitle[1]"
                      :indexValue="indexValue[2]"></GradeCategory>
                  </div>
                </div>
              </div>
              <div class="basicBox">
                <p>基础技能（25分）</p>
                <!-- 基础技能左 -->
                <div class="basicBoxMin">
                  <div class="hid"
                    :style="{ 'width': dynamicWidth[2], 'position': 'absolute', 'direction': 'rtl', 'right': '0' }">
                    <GradeCategory :score="25.00" :operate="indexOper[0]" :indexTitle="indexTitle[2]"
                      :indexValue="indexValue[0]"></GradeCategory>
                  </div>
                </div>
                <!-- 基础技能右 -->
                <div class="basicBoxMin">
                  <div class="hid" :style="{ 'width': dynamicWidth[3] }">
                    <GradeCategory :score="25.00" :operate="indexOper[1]" :indexTitle="indexTitle[2]"
                      :indexValue="indexValue[0]"></GradeCategory>
                  </div>
                </div>
              </div>
              <div class="scoreInterval" style="font-size: 2pt;">
                <span class="left-score-span">20~25 15~20 10~15 5~10 0 ~ 5</span>
                <span class="right-score-span">0 ~ 5 5~10 10~15 15~20 20~25</span>
              </div>
            </div>
          </div>
          <div class="cardContent textContent" style="width:270px;margin-left: 30px;">
            <img src="../assets/images/littleNav.png">
            <div>
              {{ textInfo[1] }}
            </div>
          </div>
        </echartsCard>

        <echartsCard :cardProp="cardProps[2]" class="clearfix">
          <div style="width:590px;" class="cardContent clearfix">
            <div class="indexScore">
              <div style="margin-top: 50px;">
                <div class="development_box">
                  <p style="color:#F19455;">校外学习（10分）</p>
                  <div class="basicBoxMin">
                    <div class="hid"
                      :style="{ 'width': dynamicWidth1[0], 'position': 'absolute', 'direction': 'rtl', 'right': '0' }">
                      <GradeCategory :score="10 * 2.5" :fullmark="10" :operate="indexOper[0]"
                        :indexTitle="indexTitle[0]" :indexValue="indexValue[2]"></GradeCategory>
                    </div>
                  </div>

                  <div class="basicBoxMin">
                    <div class="hid" :style="{ 'width': dynamicWidth1[1] }">
                      <GradeCategory :score="10 * 2.5" :fullmark="10" :operate="indexOper[1]"
                        :indexTitle="indexTitle[1]" :indexValue="indexValue[2]"></GradeCategory>
                    </div>
                  </div>
                </div>

                <div class="development_box">
                  <p style="color:#F19455;">艺术特长（10分）</p>
                  <div class="basicBoxMin">
                    <div class="hid"
                      :style="{ 'width': dynamicWidth1[2], 'position': 'absolute', 'direction': 'rtl', 'right': '0' }">
                      <GradeCategory :score="10 * 2.5" :fullmark="10" :operate="indexOper[0]"
                        :indexTitle="indexTitle[2]" :indexValue="indexValue[1]"></GradeCategory>
                    </div>
                  </div>

                  <div class="basicBoxMin">
                    <div class="hid" :style="{ 'width': dynamicWidth1[3] }">
                      <GradeCategory :score="10 * 2.5" :fullmark="10" :operate="indexOper[1]"
                        :indexTitle="indexTitle[2]" :indexValue="indexValue[1]"></GradeCategory>
                    </div>
                  </div>

                </div>
                <div class="scoreInterval1" style="color:#F19455;">
                  <span class="left-score-span">
                    <span>10~8</span>
                    <span>8~6</span>
                    <span>6~4</span>
                    <span>4~2</span>
                    <span>2~0</span>
                  </span>
                  <span class="right-score-span">
                    <span>0~2</span>
                    <span>2~4</span>
                    <span>4~6</span>
                    <span>6~8</span>
                    <span>8~10</span>
                  </span>
                </div>

              </div>
            </div>
          </div>
          <div class="cardContent textContent" style="width:270px;margin-left: 30px;">
            <img src="../assets/images/littleNav.png">
            <div>
              {{ textInfo[2] }}
            </div>
          </div>
        </echartsCard>

        <echartsCard :cardProp="cardProps[3]" class="clearfix">
          <div class="textContent">
            <img src="../assets/images/littleNav.png">
            <div>
              {{ textInfo[3] }}
            </div>
          </div>
        </echartsCard>
      </main>

    </div>
  </div>
</template>

<script>
import echartsCard from "../components/echartsCard.vue";
import BarChart from "@/components/barChart.vue";
import Radar from "@/components/radar.vue";
import LineChart from "@/components/Line.vue";
import ProgressStepChart from '@/components/ProgressStepChart.vue';
import GradeCategory from "@/components/GradeCategory.vue";
export default {
  data() {
    return {
      studyScore: ['25', '25', '25', '25'],
      devScore: ['10', '10', '10', '10'],
      stuInfo: {
        stuName: "谢汶罡",
        schoolName: "德阳天立",
        stulevel: "良好",
        stuGrade: "四年级",
        stuClass: "7班"
      },
      chartColors: [
        "#A6D7C6",
        "#E9CE68",
        "#BDDDA7",
        "#FDD23F"
      ],
      indexOper: ['unshift', 'push'],
      indexTitle: ['学生得分', '班级平均分', ''],
      indexValue: [["0~5", "5~10", "10~15", "15~20", "20~25"], ["0~2", "2~4", "4~6", "6~8", "8~10"], ["", "", "", "", ""]],
      cardProps: [{
        title: '基础指标',
        titleHeight: '33px',
        titleLeft: '28px',
        bkName: 'basicIndex.png',
        bkBorderName: 'basicIndexBk.png'
      },
      {
        title: '学业指标',
        titleHeight: '31px',
        titleLeft: '29px',
        bkName: 'studyingIndex.png',
        bkBorderName: 'studyingIndexBk.png'
      },
      {
        title: '发展指标',
        titleHeight: '55px',
        titleLeft: '20px',
        bkName: 'developIndex.png',
        bkBorderName: 'developIndexBk.png'
      },
      {
        title: '综合评价',
        titleHeight: '44px',
        titleLeft: '24px',
        bkName: 'commentIndex.png',
        bkBorderName: 'commentIndexBk.png'
      }
      ],
      textInfo: [
        '谢汶罡同学,你基础指标方面的内容都完成得很好哦。四项内容的得分率都很高,尤其是出勤率与完成度,都是满分。你参与度与课外活动的得分率也很高哦,说明你对美术学科的学习十分重视,值得表扬,以后也要继续努力呀!'
        , '谢汶罡同学,你基础指标方面的内容都完成得很好哦。四项内容的得分率都很高,尤其是出勤率与完成度,都是满分。你参与度与课外活动的得分率也很高哦,说明你对美术学科的学习十分重视,值得表扬,以后也要继续努力呀!'
        , '谢汶罡同学，在发展指标方面你的表现突出，无论是对于校外学习方面还是艺术特长方面，你的得分都高于班级平均水平，说明你很喜欢并且乐于参加美术学科的学习，要继续保持哦!',
        '谢汶罡同学，你在美术学科艺术素质测评的整体表现良好。在基础指标、学业指标和发展指标的学习中，你的表现都在班级名列前茅，值得表扬!但也不能掉以轻心哦，特别是在学业指标板块，对于创新实践、审美判断、图像识读方面的学习还需要加强。在努力学习的同时，不要丢下了你对于美术的热爱呀，相信你一定可以通过自己的努力创造出属于你的美术天地，加油哦!'
      ],
      barChartData: [98, 96, 94, 100],
      lineChartData: [
        [18.24, 15.58, 24.75, 8.0, 8.0],
        [24.0, 16.0, 24.0, 3.89, 7.86]
      ],
      radarDatas: [83.33, 66.67, 66.67, 75, 80]
    }
  },
  computed: {
    dynamicWidth() {
      const arr = [];
      for (let index = 0; index < 4; index++) {
        arr[index] = this.studyScore[index] * 240 / 25 + 'px'
      }
      return arr
    },
    dynamicWidth1() {
      const arr = [];
      for (let index = 0; index < 4; index++) {
        arr[index] = this.devScore[index] * 240 / 10 + 'px'
      }
      return arr
    },

  },
  components: { echartsCard, BarChart, Radar, LineChart, ProgressStepChart, GradeCategory }
}
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100%;
  background-image: url("../assets/images/bk.png");
  background-size: cover;
  padding: 26px;

  .main {
    width: 100%;
    height: 100%;
    background: #FDFDFA url("../assets/images/bg_grid.png") bottom left no-repeat;
    background-size: 60% 60%;
    padding: 30px;

    header {
      .logo {

        img {
          width: 90px;
          margin-right: 10px;
        }

        span {
          line-height: 100%;
          vertical-align: top;
          font-size: 16px;
          font-weight: 450;
        }
      }

      .rightExplain {
        margin-bottom: 10px;

        div {
          position: relative;
          float: right;
          width: 390px;
          height: 40px;
          line-height: 40px;
          font-size: 20px;
          font-weight: 600;
          letter-spacing: 6px;
          color: #EE7832;
          text-align: center;
          border-radius: 30px;
          background: url("../assets/images/radioBk2.png") -635px -2310px no-repeat;

          span {
            width: 100%;
          }

          img {
            position: absolute;
            left: 0;
            width: 100%;
            height: 100%;
          }
        }
      }

      .leftStuInfo {
        letter-spacing: 6px;

        .NameAndSchool>span:first-child {
          float: left;
          font-size: 35px;
          color: #EE7832;

        }

        .otherInfoTag {
          position: relative;
          float: right;
          margin: 20px 0;
          width: 220px;
          height: 25px;
          color: #646363;
          padding-left: 30px;
          background-image: url("../assets/images/classLevelBk.png");
          background-repeat: no-repeat;
          font-size: 16px;
          font-weight: 600;
          margin-right: 100px;
          margin-left: 2px;
          line-height: 25px;

          img {
            position: absolute;
            width: 25px;
            height: 26px;
            left: -3px;
            bottom: 1px;
          }
        }

      }
    }

    main {

      .colorIndex {
        float: right;

        span {
          width: 56px;
          color: #F08744;
          margin-right: 15px;

          i {
            display: inline-block;
            margin-right: 8px;
            width: 12px;
            height: 12px;
          }

        }

        span:last-child {
          margin-right: 100px;
        }


      }

      .cardContent {
        float: left;
      }


      .indexScore {
        .basicBox {
          display: flex;
          height: 40px;

          p {
            font-size: 13px;
            line-height: 40px;
            color: #565759;
          }
        }

        .scoreInterval {

          font-size: 2pt;

          .left-score-span {
            position: relative;
            left: 130px;
            top: -8px;
          }

          .right-score-span {
            position: relative;
            left: 192px;
            top: -8px;
          }


        }

        .scoreInterval1 {
          font-size: 2pt;

          .left-score-span {
            position: relative;
            display: flex;
            left: 138px;
            top: -13px;

            span {
              display: block;
              width: 38px;
            }
          }

          .right-score-span {
            position: relative;
            left: 377px;
            top: -28px;
            display: flex;

            span {
              display: block;
              width: 38px;
            }
          }
        }

      }

      .development_box {
        display: flex;
        height: 40px;

        p {
          font-size: 13px;
          line-height: 40px;
          color: #565759;
        }
      }


      .textContent {
        position: relative;
        font-size: 15px;
        color: #F08744;
        padding-top: 22px;
        letter-spacing: 2px;

        img {
          position: absolute;
          top: 0;
          left: 0;
          width: 110px;
          height: 12px;

        }
      }

      .basicBoxMin {
        width: 240px;
        height: 40px;
        position: relative;

        .hid {
          height: 40px;
          overflow: hidden;
        }
      }
    }
  }
}
</style>