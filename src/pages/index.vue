<script lang="ts" setup>
const color = reactive({
  primary: 'green',
})
</script>

<template>
  <div>
    <AppAlert>
      <div>
        <b>{{ color.primary }}</b>
      </div>
      <input
        type="text"
        v-model="color.primary"
      />
    </AppAlert>

    <NuxtPage />
  </div>
</template>

<style lang="scss">
b {
  color: v-bind('color.primary ? color.primary : "red"');
}
</style>
