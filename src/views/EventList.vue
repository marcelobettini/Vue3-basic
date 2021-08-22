<template>
  <div class="events">
    <h1>Events for Good</h1>
    <EventCard
      v-for="event in events"
      v-bind:key="event.id"
      v-bind:event="event"
    />
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
      events: [
        {
          id: 5928101,
          category: "animal welfare",
          title: "Cat Adoption Day",
          description: "Find your new feline friend at this event.",
          location: "Meow Town",
          date: "January 28, 2022",
          time: "12:00",
          petsAllowed: true,
          organiser: "Kat Laydee",
        },

        {
          id: 4528027,
          category: "sustainability",
          title: "Beach Cleanup",
          description: "Help pick up trash along the shore.",
          location: "Playa del Carmen",
          date: "July 22, 2022",
          time: "11:00",
          petsAllowed: false,
          organiser: "Carey Wales",
        },

        {
          id: 9205129,
          category: "food",
          title: "Community Gardening",
          description: "Join us as we tend to the community edible plants.",
          location: "flora City",
          date: "March 14, 2022",
          time: "10:00",
          petsAllowed: true,
          organiser: "Fern Pollin",
        },
      ],
    };
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
