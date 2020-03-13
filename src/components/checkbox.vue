<template>
  <div class="my-radio">
    <div
      v-for="(item,index) in info"
      :key="index"
    >
      <input
        ref='checkbox'
        type="checkbox"
        :id="index"
        :value="item"
        :checked="checking(item)"
        @change="radioChange($event)"
      >
      <!-- 如果不写for 点击label时无法选择radio -->
      <label >{{item}}</label>
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
    checked: Array,
    info: Array
  },
  data() {
    return {}
  },
  methods: {
    checking(item) {
      return this.checked.includes(item)
    },
    radioChange(event) {
      let arr = []
      this.$refs.checkbox.forEach(ele => {
        if (ele.checked) {
          arr.push(ele.value)
        }
      })
      this.$emit('change', arr)
    }
  }
}
</script>