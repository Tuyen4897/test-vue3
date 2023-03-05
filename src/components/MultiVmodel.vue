<template>
    <div id="app">
      <SalutationName
        v-model:salutation.capitalize="form.salutation"
        v-model:name.capitalize="form.name"
      />
  
      <pre>{{ form }}</pre>
    </div>
</template>

<script>
import { reactive } from 'vue'
import SalutationName from './SalutationName'

export default {
    name: 'App',
    components: {
        SalutationName
    },
    setup () {
        const form = reactive({
            salutation: '',
            name: ''
        })

        return {
            form
        }
    }
}
</script>