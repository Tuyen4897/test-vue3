<template>
  <div>
    Search for <input v-model="searchInput" /> 
    <div>
      <p>Loading: {{ getEvents.loading }}</p>
      <p>Error: {{ getEvents.error }}</p>
      <p>Number of events: {{ getEvents.results }}</p>
    </div>
  </div>
</template>
<script>
import { ref, watch } from "vue";
import usePromise from "@/composables/use-promise";

export default {
  setup() {
    const searchInput = ref("");
    const getEventCount = (input) => {
      return input.length;
    };

    const getEvents = usePromise(search =>
      getEventCount(search.value)
    );

    watch(searchInput, () => {
      if (searchInput.value !== "") {
        getEvents.createPromise(searchInput);
      } else {
        getEvents.results.value = null;
      }
    });
    return { searchInput, getEvents };
  }
};
</script>