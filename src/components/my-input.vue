<template>
  <div class="item">
    <input
      :value="value"
      @input="input($event)"
      placeholder="自定义组件的 v-model"
    />
  </div>
</template>
<script>
export default {
  //默认可不写
  model: {
    prop: 'value',
    event: 'input'
  },
  props: {
    value: String
  },
  data() {
    return {}
  },
  methods: {
    input(event) {
      this.$emit('input', event.target.value)
    }
  }
}
</script>