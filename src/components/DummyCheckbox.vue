<script>
export default {
  name: 'DummyCheckbox',
  props: {
    name: String,
    label: String,
    labelLeft: Boolean
  }
}
</script>

<template>
  <label :for="name">
    {{ labelLeft ? label : null }}
    <input
      type="checkbox"
      :name="name"
      :id="name"
      @change="$emit('checkChange', 'checkChange', $event)"
    />
    {{ !labelLeft ? label : null }}
  </label>
</template>

<style scoped></style>
