<script setup lang="ts">
import EventCard from '@/components/EventCard.vue'
import CardOrganCate from '@/components/CardOrganCate.vue'
import type { Event } from '@/types'
import { ref, onMounted } from 'vue'
import axios from 'axios'

const events = ref<Event[] | null>(null)

onMounted (() => {
  axios
    .get('https://my-json-server.typicode.com/Prototean/Hezela.db/db')
    .then((response) => {
      console.log(response.data)
    })
    .catch((error) => {
      console.error('There was an error!', error)
    })
})
</script>


<template>
  <h1>Events For Good</h1>
  <div class="home" v-for="event in events" :key="event.id" >
    <CardOrganCate :event="event"/> 
    <EventCard  :event="event"/>
  </div>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>