<script setup lang="ts">
import { useRouter } from 'vue-router'
import { toRefs } from 'vue'
import { type Event } from '@/types'
import { useMessageStore } from '@/stores/message'
const props = defineProps<{
  event: Event
}>()
// eslint-disable-next-line @typescript-eslint/no-unused-vars
const { event } = toRefs(props)
const router = useRouter()
const store = useMessageStore()
const edit = () => {
  store.updateEditMessage(`The data of ${props.event.title} has been updated!`)
  setTimeout(() => {
    store.resetEditMessage()
  }, 3000)
  router.push({ name: 'event-detail-view', params: { id: props.event.id } })
}
</script>
<template>
  <p>Edit event here</p>
  <button @click="edit">Edit it!</button>
</template>
