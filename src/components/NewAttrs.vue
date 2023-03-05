<template>
  <div id="app">
    <BaseInput
      v-model="email"
      label="Email:"
      type="email"
      class="thicc"
    />

    <pre>{{ email }}</pre>
  </div>
</template>

<script>
import { ref } from 'vue'
import BaseInput from './BaseInput'

export default {
  name: 'App',
  components: {
    BaseInput
  },
  setup () {
    const email = ref('')

    return {
      email
    }
  }
}
</script>