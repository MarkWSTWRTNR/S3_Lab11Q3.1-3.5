<template>
  <label v-if="label">{{ label }}</label>
  <input
    :value="modelValue"
    :placeholder="label"
    @input="inputHandler($event)"
    v-bind="$attrs"
    class="field"
  />
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      default: ''
    },
    modelValue: {
      type: [String, Number],
      default: ''
    }
  },
  methods: {
    inputHandler(event) {
      this.$emit('update:modelValue', event.target.value)
    }
  }
}
</script>
<style scoped>
label {
  color: rgb(0, 0, 0);
}
input {
  border-radius: 50px;
  border: 1px solid #000000;
}
</style>
