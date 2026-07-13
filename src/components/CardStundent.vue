<script setup lang="ts">
import type { Student } from '@/types'
defineProps<{
  student: Student
}>()

</script>

<template>

<div class="student-class">
    <div class="student-card">
      <h2>Name: {{ student.name }} &nbsp; Surname: {{ student.surname }} </h2>
      <h3>GPA : {{ student.gpa }}</h3>
    </div>
  </div>


</template>

<style scoped>
.student-class{
  display: flex;
  justify-content: center;
}
.student-card {
  padding: 20px;
  width: 450px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
.student-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
