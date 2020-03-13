<template>
  <div class="my-radio-two">
    <myRadio
      :checked="checked"
      @change="getValue"
      :info='info'
    ></myRadio>
  </div>
</template>
<script>
import myRadio from './my-radio'
export default {
  name: 'myRadioTwo',
  components: {
    myRadio
  },
  model: {
    prop: 'checked',
    event: 'change'
  },
  props: {
    checked: String,
    info:Array
  },
  data() {
    return {}
  },
  methods: {
    getValue(value) {
      this.$emit('change', value)
    }
  }
}
</script>