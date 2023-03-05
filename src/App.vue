<template>
  <Capacity />
  --------
  <MultiVmodel />
  ------
  <NewAttrs />
  --------
  <!-- <NewSyntaxExample /> -->
</template>

<script>
import Capacity from './components/Capacity.vue'
import MultiVmodel from './components/MultiVmodel.vue'
import NewAttrs from './components/NewAttrs.vue'
// import NewSyntaxExample from './components/NewSyntax/Example.vue'

export default {
  name: 'App',
  components: {
    Capacity,
    NewAttrs,
    MultiVmodel,
    // NewSyntaxExample,
  }
}
</script>
