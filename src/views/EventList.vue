<template>
  <div class="events">
    <h1>Events For Good</h1>
    <EventCard v-for="event in events" :key="event.id" :event="event"/>
  </div>
</template>

<script>
import EventCard from '../components/EventCard'

export default {
  name: "EventList",
  components: {
    EventCard,
  },
  data() {
    return {
      
    }
  }
};
</script>
<style scoped>
  .events {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>