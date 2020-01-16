<template>
  <div>
    <button @click="changedata">查询</button>
    <greenetCommonecharts id="tenantCnt" width="50%" height="100px" :options="options1"></greenetCommonecharts>
  </div>
</template>

<script>
import greenetCommonecharts from "greenet-commonecharts";
import {getcommonechartsdata} from "@/api/commonecharts";
export default {
  name: "example",
  components: { greenetCommonecharts },
  data() {
    return {
      options1: {}
    };
  },
  methods: {
    getcommonechartsdata1() {
      console.log("aaa");
      getcommonechartsdata().then(res => {
            this.options1 = {
              backgroundColor: "#fff",
              grid: {
                top: "40",
                left: "20",
                right: "57",
                bottom: "30",
                containLabel: true
              },
              yAxis: [
                {
                  type: "category",
                  data: [name],
                  inverse: true,
                  axisTick: {
                    show: false
                  },
                  axisLabel: {
                    margin: 20,
                    textStyle: {
                      fontSize: 18,
                      color: "#00b4aa"
                    }
                  },
                  axisLine: {
                    show: false
                  }
                }
              ],
              xAxis: [
                {
                  type: "value",
                  position: "top",
                  axisLabel: {
                    color: "#00b4aa",
                    show: true
                  },
                  axisLine: {
                    show: false
                  },
                  splitLine: {
                    show: false
                  }
                }
              ],
              series: [
                {
                  type: "bar",
                  barWidth: 25,
                  data: [90],
                  label: {
                    normal: {
                      show: true,
                      position: "insideBottomRight",
                      formatter: "{c}%",
                      distance: 0,
                      offset: [30, 8],
                      color: "#000",
                      fontSize: 16,
                      padding: [5, 15, 10, 15]
                    }
                  },
                  itemStyle: {
                    normal: {
                      color: '#f00',
                      barBorderRadius: 14
                    }
                  }
                },
                {
                  type: "bar",
                  barWidth: 25,
                  xAxisIndex: 0,
                  barGap: "-100%",
                  data: [100],
                  itemStyle: {
                    normal: {
                      color: "#ccc",
                      barBorderRadius: 14
                    }
                  },
                  zlevel: -1
                }
              ]
            };
      });
    },
    changedata(){
      this.options1.series[0].data = [50];
    }
  },
  mounted() {
    this.getcommonechartsdata1();
  }
};
</script>

<style>
</style>