<template>
  <div class="ting-demo">
    <h1>Popover 弹出提示</h1>
    <RevealContainer :component="PopoverBase">
      <p>
        可以使用<code>position</code>属性定义<code>t-popover</code>组件弹出位置，可选择默认<code>top</code>or<code>right</code><code>bottom</code><code>left</code>。
      </p>
    </RevealContainer>

    <RevealContainer :component="PopoverHover">
      <p>
        可以使用<code>trigger</code>属性定义<code>t-popover</code>组件触发方式，可选择默认<code>click</code>or<code>hover</code>。
      </p>
    </RevealContainer>

    <Attr :data="data"></Attr>
  </div>
</template>
<script lang="ts">
import RevealContainer from "../RevealContainer.vue";
import Attr from "../Attr.vue";
import PopoverBase from "./PopoverBase.vue"
import PopoverHover from "./PopoverHover.vue"

export default {
  components: { RevealContainer, Attr },
  setup() {
    const data = [
      {
        params: 'position',
        desc: '弹出位置',
        type: 'string',
        select: 'top / right / bottom / left',
        default: 'top',
      },
      {
        params: 'trigger',
        desc: '触发方式',
        type: 'string',
        select: 'click / hover',
        default: 'click',
      },
    ]
    return {
      PopoverBase,
      PopoverHover,
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
