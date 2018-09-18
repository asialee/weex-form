<template>
  <div>
    <ListComp :data="data"></ListComp>
    <Button text="申请"
        class="btn"
        type="blue"
				:btnStyle='btnStyle'
				@wxcButtonClicked="onList"></Button>
  </div>
</template>

<script>
import data from "./components/list/data";
import ListComp from "./components/list/list";
const navigator = weex.requireModule("navigator");
var modal = weex.requireModule("modal");
import Button from "./components/button/index.vue";

export default {
  components: { ListComp, Button },
  data() {
    return {
      data
    };
  },
  created() {
    const Steve = new BroadcastChannel("Avengers");
    Steve.onmessage = function(event) {
      this.data.push({
        label: "马云的餐票申请2",
        bill: "杭州市阿里云科技有限公司",
        quantity: "15",
        date: "2018-09-18 12:01"
      });
    };
  },
  methods: {
    onList(node) {
      var startno = weex.config.bundleUrl.indexOf("index.js");
      var newpath =
        weex.config.bundleUrl.substring(0, startno) + "application.js";
      navigator.push({
        url: newpath,
        // url: "application.html",
        animated: "true"
      });
    }
  }
};
</script>

<style>
.btn {
  margin-left: 20px;
  margin-top: 40px;
}
</style>

