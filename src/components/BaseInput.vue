<template>
  <label v-if="label"> {{ label }}</label>
  <input
    v-bind="$attrs"
    class="field"
    :placeholder="label"
    :value="modelValue"
    @input="$emit('update:modelValue', $event.target.value)"
  >
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: '',
    },
  },
  modelBalue: {
    type: [String, Number],
    default: '',
  },
}
</script>

<style scoped>
  .field {
    box-shadow: 5px;
    border: black;
    height: 30px;
    width: 250px;
  }
</style>