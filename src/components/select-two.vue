<template>
  <div class="selectTwo">
    <mySelect
      :value="value"
      @input="getValue"
      :info="info"
    ></mySelect>
  </div>
</template>
<script>
import mySelect from './select'
export default {
  components: {
    mySelect
  },
  props: {
    value: String,
    info: Array
  },
  data() {
    return {}
  },
  methods: {
    getValue(value) {
      this.$emit('input', value)
    }
  }
}
</script>