<template>
  <div class="container">
    <div class="main">
      <header>
        <div class="logo-box">
          <img class="logo-img" src="../assets/images/logo.png">
          <span class="logo-span">艺术素质测评云平台</span>
        </div>

      </header>
      <main>
        <!--艺术素质测评指标-->
        <div class="art-quality-box ">
          <!--艺术素质测评指标标题-->
          <div class="art-quality-title title">
            <div class="art-quality-content content">
              <span>中小学艺术素质测评指标</span>
              <img src="../assets/images/title_bottom.png">
            </div>
          </div>
          <!--艺术素质测评指标表格-->
          <div class="art-quality-table">
            <!--table数据-->
            <div class="art-quality-content">
              <table-one :tableData="tableData1"></table-one>
            </div>
          </div>
        </div>
        <!--美术学科测评维度及解析-->
        <div class="art-subject-box">
          <!--美术学科测评维度及解析-->
          <div class="art-subject-title title">
            <div class="art-quality-content content">
              <span>中小学生美术学科测评维度及解析</span>
              <img src="../assets/images/title_bottom.png">
            </div>
          </div>
          <!--美术学科测评维度及解析表格-->
          <div class="art-subject-table">
            <!--table数据-->
            <div class="art-subject-content">
              <table-two :tableData="tableData2"></table-two>
            </div>
          </div>
        </div>
        <!--音乐学科测评维度及解析-->
        <div class="music-subject-box">
          <!--音乐学科测评维度及解析-->
          <div class="music-subject-title title">
            <div class="music-quality-content content">
              <span>中小学生音乐学科测评维度及解析</span>
              <img src="../assets/images/title_bottom.png">
            </div>
          </div>
          <!--音乐学科测评维度及解析表格-->
          <div class="music-subject-table">
            <!--table数据-->
            <div class="music-subject-content">
              <table-three :tableData="tableData3"></table-three>
            </div>
          </div>
        </div>
        <!--艺术学科总分等级标准-->
        <div class="aggregate-box">
          <!--艺术学科总分等级标准-->
          <div class="aggregate-title title">
            <div class="aggregate-content content">
              <span>中小学生艺术学科总分等级标准</span>
              <img src="../assets/images/title_bottom.png">
            </div>
          </div>
          <!--艺术学科总分等级标准-->
          <div class="aggregate-table">
            <!--table数据-->
            <div class="aggregate-content">
              <table-four :tableData="tableData4"></table-four>
            </div>
          </div>
        </div>
      </main>
      <footer>

      </footer>
    </div>
  </div>
</template>

<script>
import TableOne from "@/components/TableOne";
import TableTwo from "@/components/TableTwo";
import TableThree from "@/components/TableThree";
import TableFour from "@/components/TableFour";

export default {
  name: "TablePage",
  data() {
    return {
      tableData1: [
        {
          title1: "基础指标",
          title2: "基础知识",
          content: "音乐、美术等艺术课程学习的出勤率、参与度和学习任务完成情况",
          score: "25",
        },
        {
          title1: "基础指标",
          title2: "课外活动",
          content: "参加学校组织的艺术兴趣小组、艺术社团和各类艺术活动的表现",
          score: "15",
        },
        {
          title1: "基础指标",
          title2: "基础知识",
          content: "理解和掌握音乐、美术等艺术课程标准要求的基础知识的情况",
          score: "25",
        },
        {
          title1: "基础指标",
          title2: "基本技能",
          content: "掌握和运用音乐、美术等艺术课程标准要求的基本技能的情况",
          score: "25",
        },
        {
          title1: "基础指标",
          title2: "在校学习",
          content:
            "自主参加校外艺术学习、参与艺术实践的情况" +
            "(主要指参与社区、乡村文化艺术活动，学习优秀的民族民间艺术，欣赏高雅的文艺演出和展览等)",
          score: "10",
        },
        {
          title1: "基础指标",
          title2: "艺术特长（加分项）",
          content:
            "某一艺术项目的特长\n(包括声乐、器乐、舞蹈、戏剧、戏曲、绘画、书法等)",
          score: "10",
        },
      ],
      tableData2: [
        {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
         {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
         {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
         {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
         {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
      ],
      tableData3: [
        {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
        {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
        {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
        {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
        {
          title: "图像识别",
          content: "指对美术作品、图形、影像及其他视觉符号的观看、识别和解读。",
        },
      ],
      tableData4:[],
    }
  },
  components: {
    TableOne,
    TableTwo,
    TableThree,
    TableFour
  }
}
</script>

<style lang="scss" scoped>

.title {
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;

  .content {
    height: 37px;

    span {
      display: inline-block;
      font-size: 22px;
      width: 450px;
      height: 38px;
      text-align: center;
      letter-spacing: 5px;
      color: #ee7832;
      background: url("../assets/images/title_matrix.png") no-repeat;
    }

    img {
      position: relative;
      top: 20px;
      right: 232px;
    }
  }
}

.container {
  width: 100%;
  height: 1527px;
  background-image: url("../assets/images/bg.png");
  background-size: cover;
  padding: 26px;

  .main {
    height: 100%;
    width: 100%;
    background-color: #fff;
    background: #FDFDFA url("../assets/images/bg_grid.png") bottom left no-repeat;
    background-size: 70% 70%; 
    header {
      width: 100%;
      height: 84px;
      display: flex;
      align-items: center;

      .logo-box {
        display: flex;
        align-items: center;
        margin-left: 34px;

        .logo-img {
          height: 28px;
        }

        .logo-span {
          font-size: 20px;
          position: relative;
          top: -5px;
          left: 10px;
        }
      }

    }

    .art-quality-box {
      width: 100%;
      height: 440px;

      .art-quality-table {
        width: 100%;
        height: 306px;
        display: flex;
        justify-content: center;

        .art-quality-content {
          width: 875px;
          height: 306px;
          background: url("../assets/images/quality_table_bottom.png") no-repeat bottom;
        }
      }
    }

    .art-subject-box {
      width: 100%;
      height: 334px;

      .art-subject-table {
        width: 100%;
        height: 218px;
        display: flex;
        justify-content: center;

        .art-subject-content {
          width: 875px;
          height: 218px;
          background: url("../assets/images/art_table_bottom.png") no-repeat bottom;
        }
      }
    }

    .music-subject-box {
      width: 100%;
      height: 334px;

      .music-subject-table {
        width: 100%;
        height: 218px;
        display: flex;
        justify-content: center;

        .music-subject-content {
          width: 875px;
          height: 218px;
          background: url("../assets/images/music_table_bottom.png") no-repeat bottom;
        }
      }
    }

    .aggregate-box {
      width: 100%;
      height: 210px;

      .aggregate-table {
        width: 100%;
        height: 72px;
        display: flex;
        justify-content: center;

        .aggregate-content {
          width: 875px;
          height: 72px;
          background: url("../assets/images/aggregate_table_bottom.png") no-repeat bottom;
        }
      }
    }
  }
}

</style>