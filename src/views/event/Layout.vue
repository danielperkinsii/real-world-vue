<template>
  <div v-if="event">
    <h1>{{ event.title }}</h1>
    <div>
      <router-link :to="{ name: 'EventDetails' }"
      >Details</router-link>
      |
      <router-link :to="{ name: 'EventRegister' }"
      >Register</router-link>
      |
      <router-link :to="{ name: 'EventEdit' }"
      >Edit</router-link>
    </div>
    <router-view :event="event" />
  </div>
</template>

<script>
import EventService from '../../services/EventService';

export default {
  props: ['id'],
  data() {
    return {
      event: null,
    }
  },
  created() {
    EventService.getEvent(this.id)
    .then(res => {
      this.event = res.data;
    })
    .catch(err => console.log(err))
  }
}

</script>
