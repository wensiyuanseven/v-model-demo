<template>
  <div class="my-radio">
    <div
      v-for="(item,index) in info"
      :key="index"
    >
      <!-- 备注
      checked 预先选定复选框或单选按钮
      value 属性为 input 元素设定值。
      对于不同的输入类型，value 属性的用法也不同：
      type="button", "reset", "submit" - 定义按钮上的显示的文本
      type="text", "password", "hidden" - 定义输入字段的初始值
      type="checkbox", "radio", "image" - 定义与输入相关联的值
      注释：<input type="checkbox"> 和 <input type="radio"> 中必须设置 value 属性。
      注释：value 属性无法与 <input type="file"> 一同使用。 -->
      <input
        type="radio"
        :id="item"
        :value="item"
        :checked="item===checked"
        @change="radioChange($event)"
      >
      <!-- 如果不写for 点击label时无法选择radio -->
      <label :for="item">{{item}}</label>
    </div>
  </div>
</template>
<script>
export default {
  model: {
    prop: 'checked',
    event: 'change'
  },
  props: {
    checked: String,
    info:Array
  },
  data() {
    return {
    }
  },
  methods: {
    radioChange(event) {
      this.$emit('change', event.target.value)
    }
  }
}
</script>