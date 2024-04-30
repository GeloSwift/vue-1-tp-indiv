<template>
    <div class="events-container">
      <div
        v-for="event in events"
        :key="event.id"
        :style="calculateEventStyle(event)"
        class="event"
      >
        {{ event.id }}
      </div>
    </div>
</template>
  
<script>
  export default {
    data() {
      return {
        events: [
          { id: 1, start: 8, duration: 1, columns: [2, 3] },
          { id: 2, start: 9, duration: 1, columns: [4, 5] },
          { id: 3, start: 8, duration: 1.5, columns: [7] }
        ]
      };
    },
    methods: {
      calculateEventStyle(event) {
        const columnWidth = 100; // Width of each column in pixels
        const eventStart = event.start * columnWidth; // Start position in pixels
        const eventWidth = event.duration * columnWidth; // Width in pixels
  
        const topPosition = 50; // Adjust this according to your layout
  
        return {
          position: 'absolute',
          left: `${eventStart}px`,
          width: `${eventWidth}px`,
          top: `${topPosition}px`
        };
      }
    }
  };
</script>
  
<style>
  .events-container {
    position: relative;
    width: 700px; /* Adjust according to your layout */
    height: 200px; /* Adjust according to your layout */
    border: 1px solid #ccc; /* Just for visualization */
  }
  
  .event {
    border: 1px solid #000; /* Just for visualization */
    background-color: lightblue; /* Just for visualization */
    height: 50px; /* Adjust according to your layout */
  }
</style>
  