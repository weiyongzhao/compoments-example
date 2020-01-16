<template>
  <div>

    <greenetLayout :titlename="initData">
      <template v-slot:greenetTitle>
        <button style="float:right">aaa</button>
      </template>
      <template v-slot:greenetContent>
        <div style="height:400px">内容区域</div>
      </template>
    </greenetLayout>

<div style="margin:20px">没有标题的布局</div>
     <greenetLayout>
      <template v-slot:greenetContent>
        <div style="height:400px">内容区域</div>
        <button @click="aaaa">查询</button>
    <br>
    <Select ref="getInput" :selectoption="selectoption" :value="value" @selectchange="aaa"/>
      </template>
    </greenetLayout>    
  </div>
</template>

<script>
import greenetLayout from "greenet-layout";
import Select from "greenet-select";
export default {
  name: "example",
  components: { greenetLayout,Select },
  data() {
    return {
      initData: "有标题的布局",
       selectoption: [
        {
          value: "选项1",
          label: "北京"
        },
        {
          value: "选项2",
          label: "上海",
          disabled: false
        },
        {
          value: "选项3",
          label: "重庆"
        },
        {
          value: "选项4",
          label: "四川"
        },
        {
          value: "选项5",
          label: "西藏"
        }
      ],
      value: ''
    };
  },
  methods: {
    aaa(a) {
      console.log(this.value);
      this.value = a;
      console.log(this.value);
    },
    aaaa() {
      console.log(this.$refs.getInput.value)
      console.log(this.value)
    }
  },
};
</script>

<style>
</style>