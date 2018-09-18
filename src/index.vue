<template>
  <div>
    <ListComp @onNodeClick="onList" :data="data"></ListComp>
  </div>
</template>

<script>
import data from "./components/list/data";
import ListComp from "./components/list/list";
const navigator = weex.requireModule("navigator");
var modal = weex.requireModule("modal");

export default {
  components: { ListComp },
  data() {
    return {
      data
    };
  },
  created() {
    // modal.toast({ message: "callback: " + weex.config.bundleUrl });
  },
  methods: {
    onList(node) {
      navigator.push(
        {
          url: "/application.html",
          animated: "true"
        }
      );
    }
  }
};
</script>

<style>
</style>

