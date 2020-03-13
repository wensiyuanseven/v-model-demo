<template>
  <div class="item">
     <div style="display:none">aaaaa</div>
    <h3>v-model.lazy ( 在“change”时而非“input”时更新 )</h3>
    <input
      type="text"
      v-model.lazy="lazy"
    >
    <p>{{lazy}}</p>
    <h3>自定义组件的 v-model</h3>
    <myInput v-model="entry"></myInput>
    <p>{{entry}}</p>
    <h3>封装第三方组件使用v-model</h3>
    <myInputTwo v-model="entryTwo"></myInputTwo>
    <p>{{entryTwo}}</p>
    <h3>在不是input组件上使用v-model实现双向绑定</h3>
    <button @click="show">显示</button>
    <noInput v-model="visible"></noInput>

    <h3>用组件封装单选框</h3>
    <myRadio
      v-model="radio"
      :info="['one', 'two']"
    ></myRadio>
    <p>{{radio}}</p>
    <h3>封装第三方组件的单选框</h3>
    <myRadioTwo
      v-model="redioTwo"
      :info="['three', 'Four']"
    ></myRadioTwo>
    <p>{{redioTwo}}</p>
    <h3>用组件封装复选框</h3>
    <checkbox
      v-model="checkboxArr"
      :info="['one', 'two','three', 'Four']"
    ></checkbox>
    <p>{{checkboxArr}}</p>
    <h3>封装第三方组件的复选框</h3>
    <checkboxTwo
      v-model="checkboxArrTwo"
      :info="['A', 'B','C', 'D']"
    ></checkboxTwo>
    <p>{{checkboxArrTwo}}</p>
    <h3>用组件封装下拉选择框【单选】</h3>
    <mySelect
      v-model="selectValue"
      :info="['A','B','C']"
    ></mySelect>
    <p>{{selectValue}}</p>
    <h3>封装第三方组件的下拉框【单选】</h3>
    <selectTwo
      v-model="selectValueTwo"
      :info="['E','F','G']"
    ></selectTwo>
    <p>{{selectValueTwo}}</p>
    <selectMultiple
      v-model="selectMultipleArr"
      :info="['A','B','C','D','E','F','G']"
    ></selectMultiple>
    <p>{{selectMultipleArr}}</p>
  </div>
</template>
<script>
import myInput from './my-input'
import myInputTwo from './my-input-two'
import noInput from './no-input'
import myRadio from './my-radio'
import myRadioTwo from './my-radio-two'
import checkbox from './checkbox'
import checkboxTwo from './checkbox-two'
import mySelect from './select'
import selectTwo from './select-two'
import selectMultiple from './select-multiple'
export default {
  props: {},
  components: {
    myInput,
    myInputTwo,
    noInput,
    myRadio,
    myRadioTwo,
    checkbox,
    checkboxTwo,
    mySelect,
    selectTwo,
    selectMultiple
  },
  data() {
    return {
      entry: '',
      entryTwo: '',
      lazy: '',
      visible: false,
      radio: 'two',
      redioTwo: 'three',
      checkboxArr: ['one', 'three'],
      checkboxArrTwo: ['A', 'D'],
      selectValue: 'C',
      selectValueTwo: 'E',
      selectMultipleArr: ['C', 'D']
    }
  },
  watch: {
    // visible(val) {
    //   debugger
    // }
  },
  methods: {
    show() {
      this.visible = true
    }
  }
}
</script>

<style>
</style>