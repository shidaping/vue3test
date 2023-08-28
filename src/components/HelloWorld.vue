<script setup lang="ts">
defineProps<{
  modelValue: string
}>()

const emit = defineEmits(['update:modelValue'])
const onUpdate = (e) => {
  emit('update:modelValue', e.target.value);
}
</script>

<template>
  <div class="greetings">
    <input :value="modelValue" @input = "onUpdate"/>
    <!-- <h1 class="green">{{ msg }}</h1> -->
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
