<template>
  <div class="checkBoxTwo">
    <checkbox
      :checked="checked"
      :info="info"
      @change="getChange"
    ></checkbox>
  </div>
</template>
<script>
import checkbox from './checkbox'
export default {
  model: {
    prop: 'checked',
    event: 'change'
  },
  props: {
    checked: Array,
    info: Array
  },
  components: {
    checkbox
  },
  methods: {
    getChange(value) {
      this.$emit('change', value)
    }
  }
}
</script>