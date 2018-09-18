<template>
  <div class="form-list-comp">
    <div class="flex-both content" v-for="item of data" :key="item.id">
      <text class="text">{{item.label}}</text>
      <input class="input" v-if="item.type && item.type === 'input'" :placeholder="item.info" />
      <text class="text" v-else>{{item.content}}</text>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    data: {
      type: Array
    }
  }
};
</script>

<style>
.flex-both {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
}
.content {
  background-color: white;
  margin-bottom: 4px;
  padding: 5px 10px;
}

.input {
  width: 300px;
  text-align: right;
}

.text {
  font-size: 32px;
}
</style>


