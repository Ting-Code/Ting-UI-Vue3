<template>
  <div class="ting-demo">
    <h1>Input 输入框</h1>
    <RevealContainer :component="InputValue">
      <p>
        可以使用<code>v-model</code>动态双向绑定一个<code>Value</code>。
      </p>
    </RevealContainer>
    <RevealContainer :component="InputDisabled">
      <p>
        可以使用<code>disabled</code>属性定义禁止状态，它接受一个<code>Boolean</code>值。
      </p>
    </RevealContainer>
    <RevealContainer :component="InputReadOnly">
      <p>
        可以使用<code>readonly</code>属性定义只读状态，它接受一个<code>Boolean</code>值。
      </p>
    </RevealContainer>

    <RevealContainer :component="InputError">
      <p>
        可以使用<code>error</code>属性定义错误提示，它接受错误内容字符串。
      </p>
    </RevealContainer>

    <RevealContainer :component="InputClear">
      <p>
        可以使用<code>clearable</code>属性定义一键清除，它接受一个<code>Boolean</code>值。
      </p>
    </RevealContainer>

    <RevealContainer :component="InputBase">
      <p>
        可以使用<code>t-password</code>组件实现展示隐藏密码
      </p>
    </RevealContainer>
    <Attr :data="data"></Attr>
  </div>
</template>
<script lang="ts">
import RevealContainer from "../RevealContainer.vue";
import Attr from "../Attr.vue";
import InputBase from "./InputPassword.vue";
import InputValue from "./InputValue.vue";
import InputDisabled from "./InputDisabled.vue";
import InputReadOnly from "./InputReadOnly.vue";
import InputError from "./InputError.vue";
import InputClear from "./InputClear.vue";

export default {
  components: { RevealContainer, Attr },
  setup() {
    const data = [
      {
        params: 'disabled',
        desc: '禁止状态',
        type: 'boolean',
        select: 'false / true',
        default: 'false',
      },
      {
        params: 'readonly',
        desc: '只读状态',
        type: 'boolean',
        select: 'false / true',
        default: 'false',
      },
      {
        params: 'error',
        desc: '错误提示',
        type: 'string',
        select: '错误提示字符串',
        default: 'null',
      },
      {
        params: 'clearable',
        desc: '一键清除内容',
        type: 'boolean',
        select: 'false / true',
        default: 'false',
      },
    ]
    return {
      InputBase,
      InputValue,
      InputDisabled,
      InputReadOnly,
      InputError,
      InputClear,
      data
    };
  },
};
</script>

<style lang="scss" scoped>
.ting-demo{
  max-width: 800px;
  h1{
    font-size: 28px;
  }
  code{
    background-color: #e2fafa;
    border-radius: 2px;
    padding: 3px 5px;
    margin: 0 3px;
  }
}
</style>

