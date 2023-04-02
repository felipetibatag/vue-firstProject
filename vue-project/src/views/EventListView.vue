<script setup>
import EventCard from "@/components/EventCard.vue";
import { ref } from "vue";
const events = ref([{
  id: 1,
  category: 'Animal 1',
  title: 'titulo1',
  description: 'description de la cosa 1',
  location: 'bogota',
  date: 'Enero 20 2023',
  time: '13:00',
  petsAllowed: true,
  organizer: 'Organizador 1'

}, {
  id: 2,
  category: 'Animal 2',
  title: 'titulo 2',
  description: 'description de la cosa 2',
  location: 'bogota',
  date: 'Enero 20 2023',
  time: '13:00',
  petsAllowed: true,
  organizer: 'Organizador 2'

}, {
  id: 3,
  category: 'Animal welfare 3',
  title: 'titulo 3',
  description: 'description de la cosa 3',
  location: 'bogota',
  date: 'Enero 20 2023',
  time: '13:00',
  petsAllowed: true,
  organizer: 'Organizador 3'

}
])
</script>

<template>
  <div class="events">
    <h1>Tablon Eventos</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>