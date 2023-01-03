<script>
import { DummyButton, DummyCheckbox, DummyModal } from './components'

export default {
  name: 'App',
  components: {
    DummyButton,
    DummyCheckbox,
    DummyModal
  },

  methods: {
    log() {
      console.log(...arguments)
    },
  },
}
</script>

<template>
  <main>
    <DummyButton
      label="oi"
      @btnClick="log"
    >
      <span>teste</span>
    </DummyButton>

    <DummyCheckbox label="check" @checkChange="log" name="teste"/>

    <DummyModal>oi</DummyModal>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
