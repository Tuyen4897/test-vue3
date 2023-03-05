<template>
  <div>
    <p>Spaces Left: {{ spacesLeft }} out of {{ capacity }}</p>
    <h2>Attending</h2>
    <ul>
      <li v-for="(name, index) in attending" :key="index">
        {{ name }}
      </li>
    </ul>
    <button @click="increaseCapacity()">Increase Capacity</button>
  </div>
</template>
<script>
import useEventSpace from "@/use/event-space";
// import { ref, computed } from "vue";
// import { toRefs, computed, reactive } from "vue";
export default {
  async setup() {
    // const capacity = ref(3);
    // const attending = ref(["Tim", "Bob", "Joe"]);

    // const spacesLeft = computed(() => {
    //   return capacity.value - attending.value.length;
    // });

    // function increaseCapacity() { 
    //   capacity.value++;
    // }

    // const event = reactive({
    //   capacity: 4,
    //   attending: ["Tim", "Bob", "Joe"],
    //   spacesLeft: computed(() => {
    //     return event.capacity - event.attending.length;
    //   })
    // });
    // function increaseCapacity() { 
    //   event.capacity++;
    // }
    // return { ...toRefs(event), increaseCapacity };
    // return { capacity, increaseCapacity, spacesLeft, attending };

    
    // onBeforeMount(() => {
    //   console.log("Before Mount!");
    // });
    // onMounted(() => {
    //   console.log("Mounted!");
    // });
    // onBeforeUpdate(() => {
    //   console.log("Before Update!");
    // });
    // onUpdated(() => {
    //   console.log("Updated!");
    // });
    // onBeforeUnmount(() => {
    //   console.log("Before Unmount!");
    // });
    // onUnmounted(() => {
    //   console.log("Unmounted!");
    // });
    // onActivated(() => {
    //   console.log("Activated!");
    // });
    // onDeactivated(() => {
    //   console.log("Deactivated!");
    // });
    // onErrorCaptured(() => {
    //   console.log("Error Captured!");
    // });
    const { capacity, attending, spacesLeft, increaseCapacity } = await useEventSpace();
    return { capacity, attending, spacesLeft, increaseCapacity };
  }
};
</script>