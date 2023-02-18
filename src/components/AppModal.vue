<template>
  <Teleport to="body">
    <div class="modal">
      <div class="modal-content">
        <slot />
      </div>
    </div>
  </Teleport>
</template>

<style lang="scss">
  .modal {
    background: rgba(#000, 0.5);
    backdrop-filter: blur(4px);
    position: absolute;
    z-index: 5;
    inset: 0;
    display: grid;
    place-items: center;
  }
</style>
