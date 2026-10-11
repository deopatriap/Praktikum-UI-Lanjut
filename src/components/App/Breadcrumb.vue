<script setup>
import { computed } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()

const breadcrumbs = computed(() => {
  const matched = route.matched
  const crumbs = matched
    .map((record) => {
      let path = record.path
      if (path.includes(':')) {
        path = route.path
      }
      return {
        name: record.name,
        path,
        meta: record.meta,
      }
    })
    .filter((record) => record.meta && record.meta.breadcrumb)

  if (route.name === 'event-detail') {
    crumbs.splice(crumbs.length - 1, 0, {
      path: '/browse/events',
      meta: { breadcrumb: 'Event List' },
    })
  }

  return crumbs
})
</script>

<template>
  <nav class="breadcrumb">
    <div class="breadcrumb-container">
      <template v-for="(crumb, index) in breadcrumbs" :key="index">
        <span v-if="index > 0" class="separator">/</span>
        <RouterLink v-if="index < breadcrumbs.length - 1" :to="crumb.path" class="breadcrumb-link">
          {{ crumb.meta.breadcrumb }}
        </RouterLink>
        <span v-else class="active-crumb">{{ crumb.meta.breadcrumb }}</span>
      </template>
    </div>
  </nav>
</template>

<style scoped>
.breadcrumb {
  margin-bottom: 2rem;
  padding: 1rem;
  background: rgb(255 255 255 / 5%);
  border-radius: 8px;
}

.breadcrumb-container {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.breadcrumb-link {
  color: var(--primary, #6644ff);
  font-weight: 500;
  text-decoration: none;
}

.breadcrumb-link:hover {
  text-decoration: underline;
}

.separator {
  color: #888;
  margin: 0 0.5rem;
}

.active-crumb {
  color: #333;
  font-weight: 600;
}
</style>
