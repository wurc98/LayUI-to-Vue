<template>
  <button class="wu-btn" :class="classObj">默认按钮</button>
</template>

<script lang="ts">
import { defineComponent, PropType, computed } from "vue";

type wButtonType = PropType<
  "primary" | "normal" | "warm" | "danger" | "disabled" | "default"
>;
type wButtonSize = PropType<"large" | "normal" | "small" | "mini">;

export default defineComponent({
  name: "WuButton",
  components: {},
  props: {
    type: {
      type: String as wButtonType,
      default: "default",
      validator: (val: string) => {
        return [
          "primary",
          "normal",
          "warm",
          "danger",
          "disabled",
          "default",
        ].includes(val);
      },
    },
    size: {
      type: String as wButtonSize,
      default: "normal",
      validator: (val: string) => {
        return ["large", "normal", "small", "mini"].includes(val);
      },
    },
    round: Boolean,
  },
  setup(props, { emit }) {
    console.log(props);
    const round = props.round;
    const classObj = computed(() => {
      let arr = ["wu-btn-" + props.type, "wu-btn-size-" + props.size];
      round?arr.push("wu-btn-radius"):null
      return arr;
    });
    return {
      classObj,
    };
  },
});
</script>
<style lang="scss">
</style>