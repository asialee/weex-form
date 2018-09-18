<template>
<div class="application-page">
  <div class="panel">
    <text class="text1">单据信息</text>
  </div>
  <FormList :data='data.data1' />
  <div class="panel secondary">
    <text class="text1">客餐申请单</text>
  </div>
  <FormList :data='data.data2' />
  <div class="prompt">
    <text class="text1">温馨提示:</text>
    <text class="text1">1.请在“用餐时间”三日内领取餐票，过期后本申请单会自动关失效；</text>
    <text class="text1">2.餐票不得跨月申请，具体信息在来客说明中详细说明。</text>
  </div>
  
  <Button text="提交"
        class="btn"
        type="blue"
				:btnStyle='btnStyle'
				@wxcButtonClicked="wxcButtonClicked"></Button>
</div>
  
</template>

<script>
import data from "./components/form-list/data.js";
import FormList from "./components/form-list/form-list";
import Button from "./components/button/index.vue";
const navigator = weex.requireModule("navigator");

export default {
  components: { FormList, Button },
  data() {
    return {
      data
    };
  },
  methods: {
    wxcButtonClicked(e) {
      
    }
  }
};
</script>

<style>
.application-page {
  background-color: #f2f2f2;
  padding-bottom: 80px;
}

.btn {
  margin-left: 20px;
}
.prompt {
  padding: 10px;
  margin: 30px 0;
}
.text {
  font-size: 32px;
}

.text1 {
  font-size: 28px;
  color: #677897;
  margin: 10px;
}

.secondary {
  margin-top: 50px;
}
</style>


