<script setup>
import EventCard from "@/components/EventCard.vue";
import { ref, onMounted } from "vue";
import EventService from '../services/EventService.js'
const events = ref(null)
onMounted(() => {
  //get events from mock db when component is created
  EventService.getEvents()
    .then((response) => {
      events.value = response.data
    })
    .catch((error) => {
      console.log(error)
    })
})
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