<template>
  <div>
    Search for <input v-model="searchInput" /> 
    <div>
      <p>Number of events: {{ results }}</p>
    </div>
  </div>
</template>
<script>
import { ref, watch } from "vue";

export default {
    name: 'SearchExample',
    setup() {
      const searchInput = ref("");
      const results = ref(0);
      
      // watchEffect(() => {
      //   results.value = searchInput.value.length;
      // });

      // watch(searchInput, (newVal, oldVal) => {
      //   ...
      // });

      // watch([firstName, lastName], () => {
      //   ...  
      // });

      // watch([firstName, lastName], ([newFirst, newLast], [oldFirst, oldLast]) => {
      //   ...   
      // });

      watch(searchInput, () => {
        results.value = searchInput.value.length;
      });

      return { searchInput, results };
    }
};
</script>