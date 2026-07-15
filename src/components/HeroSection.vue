<template>
  <section class="hero">
    <div class="hero__content">
      <p class="hello">hello<span class="hello__dot">.</span></p>
      <h1 class="hero__title">Boris Knyazhevsky</h1>

      <div class="skills">
        <p class="skills__role">Software Engineer</p>
        <ul class="skills__list">
          <li v-for="skill in skills" :key="skill" class="skills__item">{{ skill }}</li>
        </ul>
      </div>

      <nav aria-label="Professional profiles" class="hero__links">
        <a
          v-for="link in links"
          :key="link.name"
          class="hero__link"
          :href="link.url"
          rel="noopener noreferrer"
          target="_blank"
        >
          {{ link.name }}
          <AppIcon name="arrow-right" :size="18" />
        </a>
      </nav>
    </div>

    <div class="hero__photo">
      <img alt="Boris Knyazhevsky" class="hero__img" src="/img/me.png" />
      <div class="ball__orbit">
        <div class="ball__satellite"></div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import AppIcon from './AppIcon.vue'

const skills = ['.NET', 'TypeScript', 'Vue.js', 'Angular', 'Linux'] as const

const links = [
  {
    name: 'GitHub',
    url: 'https://github.com/knyazhevsky',
  },
  {
    name: 'LinkedIn',
    url: 'https://www.linkedin.com/in/boris-knyazhevsky-328090107/',
  },
] as const
</script>

<style lang="scss" scoped>
.hello {
  font-size: var(--font-size-caption);
  line-height: var(--line-height-caption);
  margin: 0 0 var(--spacing-8);
  text-transform: uppercase;

  &__dot {
    color: var(--color-accent);
  }
}

.hero {
  align-items: start;
  display: grid;
  grid-template-columns: 40fr 60fr;
  padding-bottom: var(--spacing-96);
  padding-top: var(--spacing-64);

  &__content {
    display: flex;
    flex-direction: column;
  }

  &__title {
    margin-bottom: var(--spacing-24);
  }

  &__photo {
    align-items: flex-start;
    display: flex;
    justify-content: center;
    margin-right: calc(-1 * var(--spacing-64));
    position: relative;
  }

  &__img {
    filter: brightness(0.8) contrast(1.05) drop-shadow(0 0 24px rgb(119 232 200 / 20%));
    height: auto;
    mask-image: linear-gradient(to bottom, black 80%, transparent 98%);
    max-width: unset;
    width: 110%;
    z-index: 2;

    &:hover {
      filter: brightness(0.9) contrast(1.03) drop-shadow(0 0 24px rgb(119 232 200 / 30%));
    }
  }

  &__links {
    display: flex;
    gap: var(--spacing-34);
    margin-top: var(--spacing-48);
    padding-top: var(--spacing-24);
    position: relative;

    &::before {
      border-top: var(--main-border);
      content: '';
      left: 0;
      position: absolute;
      top: 0;
      width: var(--spacing-48);
    }
  }

  &__link {
    align-items: center;
    color: var(--color-text-primary);
    display: inline-flex;
    gap: var(--spacing-8);

    &:hover {
      color: var(--color-accent);
      text-decoration: none;
    }
  }
}

.ball {
  &__orbit {
    animation: rotate 40s linear infinite;
    aspect-ratio: 1 / 1;
    border: 1px solid rgb(255 255 255 / 10%);
    border-radius: 50%;
    left: 50%;
    pointer-events: none;
    position: absolute;
    top: 0;
    transform: translateX(-50%);
    width: 450px;
    z-index: 1;
  }

  &__satellite {
    aspect-ratio: 1;
    background: var(--color-accent);
    border-radius: 50%;
    left: 0;
    position: absolute;
    top: 50%;
    transform: translateY(-50%) translateX(-50%);
    width: 10px;
  }
}

.skills {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-4);

  &__role {
    color: var(--color-text-primary);
    margin: 0;
  }

  &__list {
    display: flex;
    gap: var(--spacing-16);
    list-style: none;
    margin: 0;
    padding: 0;
  }

  &__item {
    color: var(--color-text-secondary);
  }
}

@keyframes rotate {
  0% {
    transform: translateX(-50%) rotate(0deg);
  }

  100% {
    transform: translateX(-50%) rotate(360deg);
  }
}
</style>
