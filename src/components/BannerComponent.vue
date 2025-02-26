<script setup>
const props = defineProps({
  text: String,
  repeat: { type: Number, default: 20 },
  styled_el: { type: Number, default: -1 }
})
</script>

<template>
  <div class="marquee">
    <span class="marquee__content">
      <span class="marquee_element" v-for="e in Array(repeat).keys()" :key="e">
        <span class="special_element" v-if="e === styled_el"> {{ props.text }} </span>
        <span v-else> {{ props.text }} </span>
      </span>
    </span>
    <span class="marquee__content">
      <span class="marquee_element" v-for="e in Array(repeat).keys()" :key="e">
        <span class="special_element" v-if="e === styled_el"> {{ props.text }} </span>
        <span v-else> {{ props.text }} </span>
      </span>
    </span>
  </div>
</template>

<style scoped>
.special_element {
  color: var(--maroon);
  font-weight: bold;
  text-transform: uppercase;
}

.marquee {
  --gap: 1ch;
  display: flex;
  overflow: hidden;
  gap: var(--gap);
  margin-bottom: -2px;
}

.marquee__content {
  flex-shrink: 0;
  /* display: flex; */
  justify-content: space-around;
  min-width: 100%;
  gap: var(--gap);
  animation: scroll 50s linear infinite;
}

@keyframes scroll {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(calc(-100% - var(--gap)));
  }
}
</style>
