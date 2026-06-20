<script setup>
defineProps({
  label: {
    type: String,
    required: true,
  },
  value: {
    type: [String, Number],
    required: true,
  },
  tone: {
    type: String,
    default: 'neutral',
  },
})
</script>

<template>
  <article :class="['stat-card', `stat-card--${tone}`]">
    <span>{{ label }}</span>
    <strong>{{ value }}</strong>
  </article>
</template>

<style scoped>
.stat-card {
  padding: 18px;
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.78);
}

.stat-card span {
  display: block;
  font-size: 0.82rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.stat-card strong {
  display: block;
  margin-top: 10px;
  font-size: 2rem;
}

.stat-card--warn {
  background: var(--tone-warn-bg);
  color: var(--tone-warn-fg);
}

.stat-card--danger {
  background: var(--tone-danger-bg);
  color: var(--tone-danger-fg);
}

.stat-card--neutral {
  background: var(--tone-neutral-bg);
  color: var(--tone-neutral-fg);
}

.stat-card--info {
  background: var(--tone-info-bg);
  color: var(--tone-info-fg);
}
</style>
