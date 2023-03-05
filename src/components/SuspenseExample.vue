<template>
    <div v-if="error">Looi me roi .. {{ error }}</div>
    <Suspense v-else>
        <template #default>
            <Capacity />
        </template>
        <template #fallback>
            Loading...
        </template>
    </Suspense>
</template>
<script>
import Capacity from "@/components/Capacity.vue";
import { ref, onErrorCaptured } from "vue";
export default {
    components: { Capacity },
    setup() {
        const error = ref(null);
        onErrorCaptured((e) => {
            error.value = e;
            return true;
        });
        return { error };
    },
};
</script>