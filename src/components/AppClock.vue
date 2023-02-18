<script lang="ts" setup>
  import { getFixedClock } from '@/utils'

  const previousTitle = document.title

  const hours = ref(0)
  const minutes = ref(0)
  const seconds = ref(0)

  const interval = setInterval(() => {
    ++seconds.value
    if (seconds.value > 59) {
      seconds.value = 0
      ++minutes.value
    }

    if (minutes.value > 59) {
      minutes.value = 0
      ++hours.value
    }
  }, 1000)

  const clock = computed(() => {
    const hourTime = getFixedClock(hours.value)
    const minutesTime = getFixedClock(minutes.value)
    const secondsTime = getFixedClock(seconds.value)

    return `${hourTime}:${minutesTime}:${secondsTime}`
  })

  watchEffect(() => {
    document.title = String(clock.value)
  })

  onBeforeUnmount(() => {
    document.title = previousTitle
    clearInterval(interval)
  })
</script>

<template>
  <h3 :class="$style.clock">
    {{ clock }}
  </h3>
</template>

<style module>
  .clock {
    text-align: center;
    font-size: clamp(1.5rem, 4vw, 10rem);
  }
</style>
