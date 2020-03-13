<template>
  <div class="selectMultiple">
    <select
       ref="select"
      @input="getValue($event)"
      multiple
    >
      <option
        disabled
        value=""
      >请选择</option>
      <option
        ref="option"
        v-for="(item,index) in info"
        :key="index"
        :selected='selecting(item)'
      >{{item}}</option>
    </select>
  </div>
</template>
<script>
export default {
  // 默认可不写
  model: {
    prop: 'value',
    event: 'input'
  },
  props: {
    value: Array,
    info: Array
  },
  data() {
    return {}
  },
  methods: {
    selecting(item) {
      return this.value.includes(item)
    },
    getValue(event) {

      let arr = []
      this.$refs.option.forEach(ele => {
        if (ele.selected) {
          arr.push(ele.value)
        }
      })
      this.$emit('input', arr)
    }
  }
}
</script>