<template>
  <footer class="ftr">
    <div class="ftr__content">
      <p class="city">Almaty, Kazakhstan</p>
      <p class="copyright">&copy; 2026</p>
      <p class="ftr__aside">I use Arch, btw.</p>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.ftr {
  border-top: var(--main-border);
  color: var(--color-text-secondary);
  padding-bottom: var(--spacing-34);
  padding-top: var(--spacing-34);
  text-align: center;

  &__content {
    display: flex;
    flex-direction: column;
    gap: var(--spacing-8);
  }

  &__aside {
    color: var(--color-accent);
    font-size: var(--font-size-caption);
    line-height: var(--line-height-caption);
  }
}
</style>
