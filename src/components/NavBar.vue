<template>
  <header class="hdr">
    <nav class="navbar">
      <ul class="navbar__links text-body"></ul>
    </nav>
  </header>
</template>
<script setup lang="ts"></script>
<style lang="scss" scoped>
.hdr {
  padding-inline: var(--spacing-96);
}

.navbar {
  align-items: center;
  display: flex;
  height: var(--navbar-height);
  justify-content: flex-end;
  margin-left: auto;

  &__links {
    display: flex;
    gap: var(--spacing-8);
    list-style: none;
    margin: 0;
    padding: 0;
  }

  &__link {
    a {
      color: var(--color-text-primary);

      &:hover {
        color: var(--color-accent);
      }
    }
  }
}
</style>
