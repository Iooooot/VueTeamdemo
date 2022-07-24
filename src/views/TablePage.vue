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
              <table-one></table-one>
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
              <table-two></table-two>
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
              <table-three></table-three>
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
              <table-four></table-four>
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
import TableOne from "@/views/TableOne";
import TableTwo from "@/views/TableTwo";
import TableThree from "@/views/TableThree";
import TableFour from "@/views/TableFour";

export default {
  name: "TablePage",
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
  padding: 26px;

  .main {
    height: 100%;
    width: 100%;
    background-color: #fff;
    background-image: url("../assets/images/bg_shadow.png");

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