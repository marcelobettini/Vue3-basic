<template>
  <div v-if="!event">
    <h4>Loading...</h4>
  </div>
  <div v-else>
    <h1>Details</h1>
    <h3>{{ event.title }}</h3>
    <p>{{ event.time }} on {{ event.date }} @ {{ event.location }}</p>
    <p>{{ event.description }}</p>
  </div>
</template>

<script>
export default {
  props: ["id"],
  data() {
    return {
      event: null,
    };
  },
  created() {
    fetch(
      `https://my-json-server.typicode.com/marcelobettini/vue3-basic/events/${this.id}`
    )
      .then((res) => res.json())
      .then((data) =>
        setTimeout(() => {
          this.event = data;
        }, 300)
      );
  },
};
</script>
