<script setup lang="ts">
import type { Event } from '@/types'
defineProps<{
  event: Event
}>()

</script>

<template>

<div class="event-class">
    <div class="event-card">
      <h2>Name: {{ event.name }} &nbsp; Surname: {{ event.surname }} </h2>
      <h3>GPA : {{ event.gpa }}</h3>
    </div>
  </div>


</template>

<style scoped>
.event-class{
  display: flex;
  justify-content: center;
}
.event-card {
  padding: 20px;
  width: 450px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
