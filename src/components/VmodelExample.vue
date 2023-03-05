<template>
    <div>
      <BaseInput 
        v-model="myInput"
      />
    </div>
</template>

<script>
import BaseInput from './BaseInput'

export default {
    components: { BaseInput },
    data() {
        return {
            myInput: ''
        }
    }
}
</script>