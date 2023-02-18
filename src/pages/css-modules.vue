<template>
  <h2 :class="$style.pink">
    <b>CSS </b>
    <span :class="$style.black">modules</span>
  </h2>

  <!-- Every time a component needs interact with DOM, the component needs be wrapped in ClientOnly tag -->
  <ClientOnly>
    <AppClock />

    <!--
      - This template serves as fallback place while ClientSide component is loading
      - Perfect place to put a Skeleton Component
    -->
    <template #placeholder>
      <AppLoading />
    </template>
  </ClientOnly>
</template>

<style lang="scss" module>
  .pink {
    color: pink;

    span {
      color: cyan;
    }
  }

  .black {
    color: black;
  }
</style>
