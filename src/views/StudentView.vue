<script setup lang="ts">
import EventCard from '@/components/CardStundent.vue'
import type { Student } from '@/types'
import { ref, onMounted } from 'vue'
import EventService from '@/services/EventStudent'
const students = ref<Student[] | null>(null)

onMounted (() => {
  EventService.getEvents()
    .then((response) => {
      students.value = response.data
    })
    .catch((error) => {
      console.error('There was an error!', error)
    })
})
</script>


<template>
  <h1>Student List</h1>
  <div class="student" v-for=" student in students" :key="student.id">
    <EventCard  :student="student"/>
  </div>
</template>

<style scoped>
.Students {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>