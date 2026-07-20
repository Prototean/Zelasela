<script setup lang="ts">
import { useRouter } from 'vue-router'
import { toRefs } from 'vue'
import { type Event } from '@/types'
const props = defineProps<{
    event: Event
}>()
// eslint-disable-next-line @typescript-eslint/no-unused-vars
const { event } = toRefs(props)
const router = useRouter()
const register = () => {
    // If the registration API call successful
    // Push back to the event details view
    router.push({ name: 'event-detail-view'})
}
</script>
<template>
    <p>Register event here</p>
    <button @clikc="register">Register</button>
</template>