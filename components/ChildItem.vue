<script setup>
    import { computed } from 'vue'

    const props = defineProps({
        modelValue: String
    })
    const emit = defineEmits(["update:modelValue"])

    const name = computed({
        get: () => props.modelValue,
        set: (value) => emit("update:modelValue", value)
    })
</script>

<template>
    <input v-model="name" placeholder="Write user name">
</template>