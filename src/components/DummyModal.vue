<script>
import Teleport from 'vue2-teleport'
import { DummyButton } from '.'

export default {
  name: 'DummyModal',
  components: {
    DummyButton,
    Teleport,
  },

  data() {
    return {
      open: false,
    }
  },
}
</script>

<template>
  <div>
    <button @click="open = true">Modal</button>

    <Teleport
      v-if="open"
      to="body"
    >
      <div
        class="modal"
        @click.self="open = false"
      >
        <DummyButton
          @btnClick="open = false"
          label="x"
        />

        <div class="content">
          <slot />
        </div>
      </div>
    </Teleport>
  </div>
</template>

<style scoped>
.modal {
  position: fixed;
  z-index: 10;
  top: 0;
  left: 0;
  width: 100%;
  max-width: 100%;
  min-height: 100vh;
  background: rgba(3, 3, 3, 0.5);
  backdrop-filter: blur(2px);
}

.content {
  background: #fff;
  border-radius: 5px;
  width: fit-content;
  padding: 0.5em 1em;
}
</style>
