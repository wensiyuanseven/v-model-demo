<template>
  <div class="select">
    <select @input="getValue($event)">
      <option
        disabled
        value=""
      >请选择</option>
      <option
        v-for="(item,index) in info"
        :key="index"
        :selected='item===value'
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
    value: String,
    info: Array
  },
  data() {
    return {}
  },
  methods: {
    getValue(event) {
      this.$emit('input', event.target.value)
    }
  }
}
</script>