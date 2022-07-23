<template>
  <div class="container">
    <div class="main">
      <header class="clearfix">
        <!-- 头部logo -->
        <div class="logo">
          <img src="../assets/image/logo.png" alt="logo">
          <span>艺术素质测评云平台</span>
        </div>
        <!-- 头部右侧的图表说明 -->
        <div class="rightExplain clearfix">
          <!-- 说明标签 -->
          <div>
            <span>美术学科艺术素质测评情况</span>
            <img src="../assets/image/圆角矩形边框.png" alt="border"/>
          </div>
        </div>
        <!-- 头部左侧的学生信息 -->
        <div class="leftStuInfo">
          <div class="NameAndSchool clearfix">
            <span>{{stuName}}</span>
            <span class="otherInfoTag"><img src="../assets/image/班级.png" alt=""><span style="letter-spacing:26px;">学</span>校：{{schoolName}}</span>
          </div>
          <div class="OtherInfo">
            <span class="otherInfoTag"><img src="../assets/image/班级.png" alt=""><span style="letter-spacing:26px;">班</span>级：{{StuClass}}</span>
            <span class="otherInfoTag"><img src="../assets/image/年级.png" alt=""><span style="letter-spacing:26px;">年</span>级：{{StuGrade}}</span>
            <span class="otherInfoTag"><img src="../assets/image/等级.png" alt=""><span style="letter-spacing:26px;">等</span>级：{{Stulevel}}</span>
          </div>
        </div>
      </header>
      <main>
        <div class="clearfix">
          <div class="colorIndex clearfix">
            <span><i :style="{backgroundColor: chartColors[0]}"></i>最高分</span>
            <span><i :style="{backgroundColor: chartColors[1]}"></i>平均分</span>
            <span><i :style="{backgroundColor: chartColors[2]}"></i>最低分</span>
            <span><i :style="{backgroundColor: chartColors[3]}"></i>最低分</span>
          </div>
          <echartsCard :cardProp="cardProps[0]" class="clearfix">
            <div style="width:570px;height: 180px;background-color: black;" class="cardContent"></div>
            <div class="cardContent textContent" style="width:270px;margin-left: 30px;">
                <img src="../assets/image/小导航.png">
                <div>
                  谢汶罡同学,你基础指标方面的内容都完成得很好哦。四项内容的得分率都很高,尤其是出勤率与完成度,都是满分。
                  你参与度与课外活动的得分率也很高哦,说明你对美术学科的学习十分重视,值得表扬,以后也要继续努力呀!
                </div>
            </div>
          </echartsCard>
        </div>

        <echartsCard :cardProp="cardProps[1]" class="clearfix">
            <div style="width:590px;height: 300px;background-color: black;" class="cardContent"></div>
            <div class="cardContent textContent" style="width:270px;margin-left: 30px;">
                <img src="../assets/image/小导航.png">
                <div>
                  谢汶罡同学,你基础指标方面的内容都完成得很好哦。四项内容的得分率都很高,尤其是出勤率与完成度,都是满分。
                  你参与度与课外活动的得分率也很高哦,说明你对美术学科的学习十分重视,值得表扬,以后也要继续努力呀!
                </div>
            </div>
          </echartsCard>

          <echartsCard :cardProp="cardProps[2]" class="clearfix">
            <div style="width:590px;height: 85px;background-color: black;" class="cardContent"></div>
            <div class="cardContent textContent" style="width:270px;margin-left: 30px;">
                <img src="../assets/image/小导航.png">
                <div>
                  谢汶罡同学，在发展指标方面你的表现突出，无论是对于校外学习方面还是艺术特长方面，你的得分都高于班级平均水平，
                  说明你很喜欢并且乐于参加美术学科的学习，要继续保持哦!
                </div>
            </div>
          </echartsCard>

          <echartsCard :cardProp="cardProps[3]" class="clearfix">
            <div class="textContent">
                <img src="../assets/image/小导航.png">
                <div>
                  谢汶罡同学，你在美术学科艺术素质测评的整体表现良好。在基础指标、学业指标和发展指标的学习中，你的表现都在班级名列前茅，
                  值得表扬!但也不能掉以轻心哦，特别是在学业指标板块，对于创新实践、审美判断、图像识读方面的学习还需要加强。
                  在努力学习的同时，不要丢下了你对于美术的热爱呀，相信你一定可以通过自己的努力创造出属于你的美术天地，加油哦!
                </div>
            </div>
          </echartsCard>
      </main>

    </div>
  </div>
</template>

<script>
import echartsCard from "../components/echartsCard.vue";
export default {
    data() {
        return {
            stuName: "谢汶罡",
            schoolName: "德阳天立",
            Stulevel: "良好",
            StuGrade: "四年级",
            StuClass: "7班",
            chartColors: [
                "#A6D7C6",
                "#E9CE68",
                "#BDDDA7",
                "#FDD23F"
            ],
            cardProps:[{
                title:'基础指标',
                titleHeight:'33px',
                titleLeft:'28px',
                bkName:'基础指标.png',
                bkBorderName:'基础指标边框.png'
              },
              {
                title:'学业指标',
                titleHeight:'31px',
                titleLeft:'29px',
                bkName:'学业指标.png',
                bkBorderName:'学业指标边框.png'
              },
              {
                title:'发展指标',
                titleHeight:'55px',
                titleLeft:'20px',
                bkName:'发展指标.png',
                bkBorderName:'发展指标边框.png'
              },
              {
                title:'综合评价',
                titleHeight:'44px',
                titleLeft:'24px',
                bkName:'综合评价.png',
                bkBorderName:'综合评价边框.png'
              }
            ]
            
          
        }
    },
    components: { echartsCard }
}
</script>

<style lang="scss" scoped>
  .container {
        width: 100%;
        height: 100%;
        background-image: url("../assets/image/背景.png");
        padding: 26px;

        .main {
          width: 100%;
          height: 100%;
          background-color: #FDFDFA;
          padding:30px;

          header{
            .logo{

              img{
                width: 90px;
                margin-right: 10px;
              }

              span{
                line-height: 100%;
                vertical-align: top;
                font-size: 16px;
                font-weight: 450;
              }
            }
              
            .rightExplain {
              margin-bottom: 10px;
              div{
                position: relative;
                float: right;
                width: 390px;
                height: 40px;
                line-height: 40px;
                font-size: 20px;
                font-weight: 600;
                letter-spacing:6px;
                color: #EE7832;
                text-align: center;
                border-radius: 30px;
                background:url("../assets/image/圆角矩形背景.png") -635px -2310px no-repeat;
                
                span{
                  width: 100%;
                }
                
                img{
                  position: absolute;
                  left: 0;
                  width: 100%;
                  height: 100%;
                }
              }
            } 

            .leftStuInfo{
              letter-spacing:6px;

              .NameAndSchool>span:first-child{
                float: left;
                font-size: 35px;
                color: #EE7832;
                
              }
              
              .otherInfoTag{
                  position: relative;
                  float: right;
                  margin: 20px 0;
                  width: 220px;
                  height: 25px;
                  color: #646363;
                  padding-left: 30px;
                  background-image: url("../assets/image/学校等级年级班级背景.png");
                  background-repeat: no-repeat;
                  font-size: 16px;
                  font-weight: 600;
                  margin-right: 100px;
                  margin-left: 2px;
                  line-height: 25px;
                  img{
                    position: absolute;
                    width: 25px;
                    height: 26px;
                    left: -3px;
                    bottom: 1px;
                  }
              }

            }
          }

          main{

            .colorIndex{
              float: right;
              span{
                width: 56px;
                color: #F08744;
                margin-right: 15px;
                i{
                  display: inline-block;
                  margin-right: 8px;
                  width: 12px;
                  height: 12px;
                }
              
              }

              span:last-child{
                margin-right: 100px;
              }


            }

            .cardContent{
              float: left;
            }

            .textContent{
              position: relative;
              font-size: 15px;
              color: #F08744;
              padding-top: 22px;
              letter-spacing: 2px;

              img{
                position: absolute;
                top: 0;
                left: 0;
                width: 110px;
                height: 12px;

              }
            }
          }
        }
    }
</style>