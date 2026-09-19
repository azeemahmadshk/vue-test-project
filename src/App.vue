<script setup lang="ts">
import { computed, ref } from 'vue'
import vueLogo from './assets/vue.svg'

const count = ref(0)
const name = ref('')

const greeting = computed(() => {
  const trimmed = name.value.trim()
  return trimmed ? `Hello, ${trimmed}` : 'Hello, Vue'
})

function increment() {
  count.value += 1
}

function reset() {
  count.value = 0
  name.value = ''
}
</script>

<template>
  <div class="page">
    <header class="hero">
      <img :src="vueLogo" class="logo" alt="Vue logo" width="72" height="72" />
      <p class="brand">Vue Test Project</p>
      <h1>{{ greeting }}</h1>
      <p class="lede">
        A minimal Vue 3 + TypeScript + Vite sandbox for checking reactivity,
        components, and hot module reload.
      </p>
    </header>

    <main class="panel">
      <label class="field">
        <span>Your name</span>
        <input
          v-model="name"
          type="text"
          placeholder="Type to update the greeting"
          autocomplete="off"
        />
      </label>

      <div class="counter-row">
        <button type="button" class="primary" @click="increment">
          Count is {{ count }}
        </button>
        <button type="button" class="ghost" @click="reset">Reset</button>
      </div>

      <p class="hint">
        Edit <code>src/App.vue</code> and save — Vite HMR should refresh this
        view without a full reload.
      </p>
    </main>
  </div>
</template>
