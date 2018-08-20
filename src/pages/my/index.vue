<template>
<div>
    <div>{{msg}}</div>
    <br />
<ul>
   <!-- <li v-for="item in list" :key="item"> -->
   <li v-for="item in list" :key="item">
       {{item}}
    </li>
</ul>
</div>
</template>

<script>
export default {
  data() {
    return {
      msg: "我是一个用户组件",
      list: []
    };
  },
  methods: {},
  created() {
    for (var i = 0; i < 10; i++) {
      this.list.push("第" + i + "个元素");
    }
  }
};
</script>

