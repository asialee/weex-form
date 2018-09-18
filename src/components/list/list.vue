<template>
  <div class="list-comp">
    <div @click="onNodeClick(item)" class="content" v-for="(item, i) of data" :key="i">
      <text class="title">{{item.label}}</text>
      <text class="gray">来客单位:{{item.bill}}</text>
      <text class="gray">餐票数:{{item.quantity}}张</text>
      <text class="gray">用餐时间:{{item.date}}</text>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array
    }
  },
  methods: {
    onNodeClick(node) {
      this.$emit("onNodeClick", node);
    }
  }
};
</script>

<style>
.content {
  border-bottom-width: 1px;
	border-bottom-style: solid;
	border-bottom-color: black;
  padding: 20px;
}
.title {
  font-size: 40px;
}
.gray {
  color: #677897;
  font-size: 32px;
}
</style>
