<script setup>
import EventCard from "@/components/EventCard.vue";
import { ref, onMounted, watchEffect, computed } from "vue";
import EventService from '../services/EventService.js'
const events = ref(null)
const totalEvents = ref(0);
const props = defineProps({
  page: null
})

watchEffect(() => {
  EventService.getEvents(2, props.page)
    .then((response) => {
      events.value = response.data
      totalEvents.value = response.headers['x-total-count']
    })
    .catch((error) => {
      console.log(error)
    })
})
const conPaginas = computed(() => {
  let totalPages = Math.ceil(totalEvents.value / 2)
  return props.page < totalPages
})
</script>

<template>
  <div class="events">
    <h1>Tablon Eventos</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event" />
    <RouterLink :to="{ name: 'event-list', query: { page: props.page - 1 } }" rel="prev" v-if="props.page != 1">Anterior</RouterLink>
    <RouterLink :to="{ name: 'event-list', query: { page: props.page + 1 } }" rel="next" v-if="conPaginas">Siguiente
    </RouterLink>
  </div>
</template>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>