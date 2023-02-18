<script lang="ts" setup>
  const appConfig = useAppConfig()
</script>

<template>
  <div class="container">
    <header>
      <div>
        <img
          src="~/assets/full-logo-green-dark.svg"
          alt="Nuxt 3 Logo"
        />
        <h1>{{ appConfig.title }}</h1>
      </div>
      <nav>
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/css-modules">CSS Modules</NuxtLink>
      </nav>
    </header>

    <div class="content">
      <slot />
    </div>

    <footer>
      <img
        src="/images/icon-black.svg"
        alt="Nuxt 3 Logo"
      />
    </footer>
  </div>
</template>

<style lang="scss">
  .container {
    display: flex;
    flex-flow: column;
    align-items: center;
    min-height: 100vh;
    padding: 1rem;
    max-width: 1024px;
    margin: 0 auto;
    gap: 50px;
  }

  nav {
    display: flex;
    flex-flow: row wrap;
    gap: 20px 10px;

    a {
      display: block;
      text-decoration: none;
      color: var(--dark);
      padding: 0.5em;
      border-radius: 8px;

      &.router-link-active {
        background: var(--dark);
        color: var(--light);
      }
    }
  }

  .content {
    width: 100%;
    flex: 1;
  }

  header,
  footer {
    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;
    align-items: flex-end;
    width: 100%;
    gap: 10px;

    img {
      width: 200px;
    }
  }

  footer {
    justify-content: center;

    img {
      width: 50px;
    }
  }
</style>
