<script lang="ts">
import { type Ref, ref, type PropType } from "vue";

export default {
  props: {
    text: String,
    count: {
      default: 0,
      type: Number
    },
    extraSettings: Object as PropType<{ name: String }>
  },
  setup(props, context) {
    let count: Ref<number> = ref(props.count);

    const increaseCount = () => {
      count.value++;
    };

    // expose to template and other options API hooks
    return {
      count,
      text: props.text,
      increaseCount
    };
  },
  mounted() {
    console.log(this.count);
    console.log(this.extraSettings);
  }
};
</script>

<template>
  <button @click="increaseCount()">{{ text }} num: {{ count }}</button>
</template>

<style scoped lang="scss">
</style>