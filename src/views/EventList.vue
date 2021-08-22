<template>
  <div class="events">
    <h1>Events for Good</h1>
    <div v-if="!events">
      <h4>Loading...</h4>
    </div>
    <div v-else>
      <EventCard
        v-for="event in events"
        v-bind:key="event.id"
        v-bind:event="event"
      />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "../components/EventCard.vue";

export default {
  name: "Home",

  components: {
    EventCard,
  },

  data() {
    return {
      events: null,
    };
  },
  created() {
    fetch("https://my-json-server.typicode.com/marcelobettini/vue3-basic/db")
      .then((res) => res.json())
      .then((data) => {
        setTimeout(() => {
          this.events = data.events;
        }, 1000);
      });
  },
};
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
  /*justify-content and align-items are similar in their behviour, the difference being that
   justify-content works on the the main axis while align-items works on the cross axis. 
   align-content works only on multi-line containers and has no effect on single line containers... */
}
</style>
