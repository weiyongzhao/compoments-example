<template>
  <div>
    <button @click="aaaa">查询</button>
    <br>
    <Select ref="getInput" :selectoption="selectoption" :value="value" @selectchange="aaa"/>
  </div>
</template>

<script>
import Select from "greenet-select";
export default {
  components: { Select },
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
  data() {
    return {
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
  }
};
</script>
