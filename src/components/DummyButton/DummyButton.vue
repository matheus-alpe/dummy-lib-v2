<script>
export default {
  name: 'DummyButton',
  props: {
    label: String,
    disabled: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<template>
  <button
    type="button"
    @click.stop="$emit('btnClick', 'btnClick', $event)"
    @focus.stop="$emit('btnFocus', 'btnFocus', $event)"
    @blur.stop="$emit('btnBlur', 'btnBlur', $event)"
    :disabled="disabled"
  >
    {{ label }}
    <slot />
  </button>
</template>

<style scoped>
button {
  border-radius: var(--border-radius);
  border: 1px solid transparent;
  padding: 0 1em;
  min-height: 2.5em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  color: var(--primary-light);

  background-color: var(--bg);
  cursor: pointer;
  transition: opacity 0.25s;
}

button:disabled {
  opacity: .4;
} 

button:hover {
  opacity: .9;
}

button:focus,
button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;
}
</style>
