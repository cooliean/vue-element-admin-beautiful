<template>
  <div class="index-container">
    <el-alert title="欲戴王冠,必承其重" type="success"
      ><a
        target="_blank"
        href="//shang.qq.com/wpa/qunwpa?idkey=00db5d4f8037fb577d128c2654de0bef68d32e55a41431b07a08a1d4446bb587"
        ><img
          border="0"
          src="//pub.idqqimg.com/wpa/images/group.png"
          alt="BYUI(vue-element-admin-beautif"
          title="BYUI(vue-element-admin-beautif"
      /></a>
      <a
        target="_blank"
        href="https://github.com/chuzhixin/vue-element-admin-beautiful"
      >
        开源地址:https://github.com/chuzhixin/vue-element-admin-beautiful
      </a>
    </el-alert>

    <div class="top-panel">
      <el-row :gutter="15">
        <el-col :xs="24" :sm="24" :md="12" :lg="6" :xl="6" class="top-panel1">
          <div class="card1">
            <div class="top-panel-content byui-clearfix">
              <div class="txt-box">
                <p class="num-box">
                  <byui-icon :icon="['fas', 'heart']"></byui-icon>
                  <span
                    >我有 <br /><byui-count
                      :start-val="config1.startVal"
                      :end-val="config1.endVal"
                      :duration="config1.duration"
                      :separator="config1.separator"
                      :prefix="config1.prefix"
                      :suffix="config1.suffix"
                      :decimals="config1.decimals"
                    />个心愿</span
                  >
                </p>
              </div>
            </div>
          </div>
        </el-col>
        <el-col :xs="24" :sm="24" :md="12" :lg="6" :xl="6" class="top-panel2">
          <div class="top-panel-content byui-clearfix">
            <img class="img-box" src="@/assets/project/project2.png" />
            <div class="txt-box">
              <p>XXX</p>
              <p class="num-box">
                <span>
                  <byui-count
                    :start-val="config1.startVal"
                    :end-val="config1.endVal"
                    :duration="config1.duration"
                    :separator="config1.separator"
                    :prefix="config1.prefix"
                    :suffix="config1.suffix"
                    :decimals="config1.decimals" /></span
                >个
              </p>
            </div>
          </div>
        </el-col>
        <el-col :xs="24" :sm="24" :md="12" :lg="6" :xl="6" class="top-panel3">
          <div class="top-panel-content byui-clearfix">
            <img class="img-box" src="@/assets/project/project3.png" />
            <div class="txt-box">
              <p>XXX</p>
              <p class="num-box">
                <span
                  ><byui-count
                    :start-val="config1.startVal"
                    :end-val="config1.endVal"
                    :duration="config1.duration"
                    :separator="config1.separator"
                    :prefix="config1.prefix"
                    :suffix="config1.suffix"
                    :decimals="config1.decimals" /></span
                >个
              </p>
            </div>
          </div>
        </el-col>
        <el-col :xs="24" :sm="24" :md="12" :lg="6" :xl="6" class="top-panel4">
          <div class="top-panel-content byui-clearfix">
            <img class="img-box" src="@/assets/project/project4.png" />
            <div class="txt-box">
              <p>XXX</p>
              <p class="num-box">
                <span
                  ><byui-count
                    :start-val="config1.startVal"
                    :end-val="config1.endVal"
                    :duration="config1.duration"
                    :separator="config1.separator"
                    :prefix="config1.prefix"
                    :suffix="config1.suffix"
                    :decimals="config1.decimals" /></span
                >个
              </p>
            </div>
          </div>
        </el-col>
        <el-col :xs="24" :sm="24" :md="12" :lg="6" :xl="6">
          <el-card shadow="never">
            <div slot="header">
              <svg-icon icon-class="advertising" /> <span>访问量</span>
            </div>
            <byui-chart autoresize theme="byui-echarts-theme" :options="fwl" />
            <div class="bottom">
              <span
                >日均访问量:

                <byui-count
                  :start-val="config1.startVal"
                  :end-val="config1.endVal"
                  :duration="config1.duration"
                  :separator="config1.separator"
                  :prefix="config1.prefix"
                  :suffix="config1.suffix"
                  :decimals="config1.decimals"
                />
              </span>
            </div>
          </el-card>
        </el-col>
        <el-col :xs="24" :sm="24" :md="12" :lg="6" :xl="6">
          <el-card shadow="never">
            <div slot="header">
              <svg-icon icon-class="cable_release" /> <span>授权数</span>
            </div>
            <byui-chart autoresize theme="byui-echarts-theme" :options="sqs" />
            <div class="bottom">
              <span
                >总授权数:
                <byui-count
                  :start-val="config2.startVal"
                  :end-val="config2.endVal"
                  :duration="config2.duration"
                  :separator="config2.separator"
                  :prefix="config2.prefix"
                  :suffix="config2.suffix"
                  :decimals="config2.decimals"
              /></span>
            </div>
          </el-card>
        </el-col>
        <el-col :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
          <el-card shadow="never">
            <div slot="header">
              <svg-icon icon-class="heat_map" /><span>词云</span>
            </div>
            <byui-chart
              autoresize
              @zr:click="handleZrClick"
              @click="handleClick"
              theme="byui-echarts-theme"
              :options="cy"
            />
            <div class="bottom">
              <span
                >词云数量:<byui-count
                  :start-val="config3.startVal"
                  :end-val="config3.endVal"
                  :duration="config3.duration"
                  :separator="config3.separator"
                  :prefix="config3.prefix"
                  :suffix="config3.suffix"
                  :decimals="config3.decimals"
              /></span>
            </div>
          </el-card>
        </el-col>

        <div
          style="
            position: fixed;
            bottom: 0px;
            right: 0;
            width: 400px;
            display: flex;
            justify-items: center;
            justify-content: center;
            align-items: center;
            align-content: center;
          "
        >
          <el-card shadow="never">
            <div slot="header">
              <svg-icon icon-class="heat_map" /><span
                >交流学习群(愿者上钩)</span
              >
            </div>
            <img src="@/assets/ewm.png" />
          </el-card>
        </div>
        <!-- <div
          class="hidden-xs-only"
          style="
            width: 400px;
            position: fixed;
            bottom: 0px;
            right: 250px;
            display: flex;
            justify-items: center;
            justify-content: center;
            align-items: center;
            align-content: center;
          "
        >
          <el-card shadow="never">
            <div slot="header">
              <svg-icon icon-class="heat_map" /><span>免费群</span>
            </div>
            <img style="width: 140px;" src="@/assets/ewm2.jpg" />
          </el-card>
        </div>-->
      </el-row>
    </div>
  </div>
</template>

<script>
import byuiChart from "@/plugins/echarts";
import byuiCount from "@/plugins/byuiCount";

export default {
  name: "Index",
  components: {
    byuiChart,
    byuiCount,
  },
  data() {
    return {
      config1: {
        startVal: 0,
        endVal: 99,
        decimals: 0,
        prefix: "",
        suffix: "",
        separator: ",",
        duration: 5000,
      },
      config2: {
        startVal: 0,
        endVal: 82,
        decimals: 0,
        prefix: "",
        suffix: "",
        separator: ",",
        duration: 3000,
      },
      config3: {
        startVal: 0,
        endVal: 12,
        decimals: 0,
        prefix: "",
        suffix: "",
        separator: ",",
        duration: 3000,
      },

      //访问量
      fwl: {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "line",
          },
        },
        grid: {
          top: "4%",
          left: "2%",
          right: "4%",
          bottom: "0%",
          containLabel: true,
        },
        xAxis: [
          {
            type: "category",
            boundaryGap: false,
            data: ["0时", "4时", "8时", "12时", "16时", "20时", "24时"],
            axisTick: {
              alignWithLabel: true,
            },
          },
        ],
        yAxis: [
          {
            type: "value",
          },
        ],
        series: [
          {
            name: "访问量",
            type: "line",
            data: [10, 52, 20, 33, 39, 33, 22],
            smooth: true,
            areaStyle: {},
          },
        ],
      }, //授权数
      sqs: {
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "line",
          },
        },
        grid: {
          top: "4%",
          left: "2%",
          right: "4%",
          bottom: "0%",
          containLabel: true,
        },
        xAxis: [
          {
            type: "category",
            /*boundaryGap: false,*/
            data: ["0时", "4时", "8时", "12时", "16时", "20时", "24时"],
            axisTick: {
              alignWithLabel: true,
            },
          },
        ],
        yAxis: [
          {
            type: "value",
          },
        ],
        series: [
          {
            name: "授权数",
            type: "bar",
            barWidth: "60%",
            data: [10, 52, 20, 33, 39, 33, 22],
          },
        ],
      },
      //词云
      cy: {
        grid: {
          top: "4%",
          left: "2%",
          right: "4%",
          bottom: "0%",
        },
        series: [
          {
            type: "wordCloud",
            gridSize: 15,
            sizeRange: [12, 40],
            rotationRange: [0, 0],
            width: "100%",
            height: "100%",
            textStyle: {
              normal: {
                color() {
                  const arr = [
                    "#1890FF",
                    "#36CBCB",
                    "#4ECB73",
                    "#FBD437",
                    "#F2637B",
                    "#975FE5",
                  ];
                  let index = Math.floor(Math.random() * arr.length);
                  return arr[index];
                },
                /*color: function() {
                                                                  return `rgb(
                                                                  ${Math.round(
                                                                      Math.random() * 255
                                                                  )} , ${Math.round(
                                                                      Math.random() * 255
                                                                  )} , ${Math.round(Math.random() * 255)} )`;
                                                              }*/
              },
            },
            data: [
              {
                name: "XXXX",
                value: 15000,
              },
              {
                name: "byui",
                value: 10081,
              },
              {
                name: "beautiful",
                value: 9386,
              },

              {
                name: "国防白皮书",
                value: 6500,
              },
              {
                name: "创新",
                value: 6000,
              },
              {
                name: "民主革命",
                value: 4500,
              },
              {
                name: "文化强国",
                value: 3800,
              },
              {
                name: "国家主权",
                value: 3000,
              },
              {
                name: "领土完整",
                value: 2300,
              },
              {
                name: "安全",
                value: 2000,
              },
              {
                name: "从严治党",
                value: 1900,
              },
              {
                name: "现代化经济体系",
                value: 1800,
              },
              {
                name: "国防动员",
                value: 1700,
              },
              {
                name: "信息化战争",
                value: 1600,
              },
              {
                name: "局部战争",
                value: 1500,
              },
              {
                name: "教育",
                value: 1200,
              },
              {
                name: "职业教育",
                value: 1100,
              },
              {
                name: "兵法",
                value: 900,
              },
              {
                name: "一国两制",
                value: 800,
              },
              {
                name: "特色社会主义思想",
                value: 700,
              },
            ],
          },
        ],
      },
    };
  },
  mounted() {},
  methods: {
    handleClick(e) {
      this.baseMessage(`点击了${e.name},这里可以写跳转`);
    },
    handleZrClick(e) {},
  },
};
</script>

<style lang="scss" scoped>
.index-container {
  width: 100%;
  box-sizing: border-box !important;
  background: #f2f2f2;
  overflow-x: hidden !important;
  .el-col {
    min-height: 200px;
  }
  .top-panel {
    width: 100%;
    height: 251px;
    background-color: #ffffff;
    margin-bottom: 10px;
    padding: 28px 20px;

    .top-panel-content {
      margin-bottom: 34px;
      padding: 20px;
      .img-box {
        width: 80px;
        height: 80px;
        float: left;
        margin-right: 20px;
      }

      .txt-box {
        width: calc(100% - 100px);
        float: left;
        font-size: 18px;
        line-height: 38px;
        color: #999;

        p.num-box {
          span {
            font-size: 40px;
            line-height: 42px;
            color: #666;
            margin-right: 10px;
          }
        }
      }
    }

    .bottom-panel-content {
      width: 100%;
      height: 81px;
      background-color: #f6f8fc;
      border-radius: 4px;
      padding: 20px 25px;

      .txt-box {
        height: 16px;
        font-size: 16px;
        line-height: 16px;
        color: #999;
        margin-bottom: 20px;
      }
    }
  }

  ::v-deep {
    .el-card__header {
      svg {
        width: 1.2em;
        height: 1.2em;
        font-size: 18px;
      }
      span {
        margin-left: 5px;
        font-size: 16px;
        color: rgb(79, 85, 110);
        font-weight: bold;
      }
    }
    .el-card__body {
      height: 200px;

      .echarts {
        width: 100%;
        height: 140px;
      }
    }
  }

  .bottom {
    margin-top: 5px;
    height: 40px;
    line-height: 40px;
    border-top: 1px solid $base-border-color;
    text-align: left;
    color: #595959;
  }
  .card1 {
    border-radius: 4px;
    background-image: -webkit-linear-gradient(
      -52deg,
      rgb(90, 94, 253) 0%,
      rgb(103, 182, 253) 100%
    );
    box-shadow: 0px 0px 9px 0px rgba(98, 83, 190, 0.44);
    height: 100px;
    padding: 20px;
    box-sizing: border-box;
    height: 180px;
    .txt-box {
      width: 100% !important;
      svg {
        color: #ffffff;
        font-size: 80px;
        position: absolute;
      }
      .num-box span {
        margin-left: 100px;
        color: #ffffff !important;
        font-size: 16px;
      }
    }
  }
}
</style>
