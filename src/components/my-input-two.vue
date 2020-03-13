<template>
  <div class="self-input">
    <myInput
      :value="value"
      @input="getValue"
    ></myInput>
  </div>
</template>
<script>
import myInput from './my-input'
export default {
  props: {
    value: String
  },
  components: {
    myInput
  },
  data() {
    return {}
  },
  computed: {},
  methods: {
    getValue(value) {
      // 直接能拿到value值
      this.$emit('input', value)
    }
  }
}
</script>