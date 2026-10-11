<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="dashboard-layout">
    <aside class="dashboard-rail">
      <RouterLink to="/" class="rail-brand">Gatherly Organizer</RouterLink>
      <nav class="rail-nav" aria-label="Dashboard navigation">
        <RouterLink to="/dashboard" class="rail-link active">Overview</RouterLink>
        <a href="#" class="rail-link">My Events</a>
        <a href="#" class="rail-link">Attendees</a>
        <a href="#" class="rail-link">QR Check-in</a>
      </nav>
      <div class="rail-footer">
        <RouterLink to="/" class="rail-link">&larr; Back to Public</RouterLink>
      </div>
    </aside>

    <main class="dashboard-pane">
      <header class="pane-header">
        <h1>Dashboard</h1>
        <span class="user-profile">Admin</span>
      </header>
      <div class="pane-content">
        <RouterView />
      </div>
    </main>
  </div>
</template>

<style scoped>
.dashboard-layout {
  display: flex;
  height: 100vh;
  overflow: hidden;
  background: var(--bg-gray);
}

.dashboard-rail {
  display: flex;
  width: 260px;
  flex-direction: column;
  flex-shrink: 0;
  color: white;
  background: var(--text-main);
}

.rail-brand {
  padding: var(--space-6);
  color: white;
  border-bottom: 1px solid rgb(255 255 255 / 10%);
  font-size: 1.2rem;
  font-weight: 700;
  text-decoration: none;
}

.rail-nav {
  display: flex;
  flex: 1;
  flex-direction: column;
  gap: var(--space-1);
  padding: var(--space-6) 0;
}

.rail-link {
  display: block;
  padding: var(--space-3) var(--space-6);
  color: #a0a0b0;
  font-weight: 500;
  text-decoration: none;
  transition:
    background-color 0.2s,
    color 0.2s;
}

.rail-link:hover,
.rail-link.active {
  color: white;
  background: rgb(255 255 255 / 10%);
}

.rail-footer {
  padding: var(--space-4) 0;
  border-top: 1px solid rgb(255 255 255 / 10%);
}

.dashboard-pane {
  display: flex;
  min-width: 0;
  flex: 1;
  flex-direction: column;
  overflow-y: auto;
}

.pane-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: var(--space-4) var(--space-8);
  background: white;
  border-bottom: 1px solid var(--border-color);
}

.pane-header h1 {
  margin: 0;
  font-size: 1.5rem;
}

.user-profile {
  color: var(--text-muted);
}

.pane-content {
  padding: var(--space-8);
}

@media (max-width: 700px) {
  .dashboard-rail {
    width: 72px;
  }

  .rail-brand {
    overflow: hidden;
    padding: var(--space-4) var(--space-2);
    font-size: 0.75rem;
    text-align: center;
  }

  .rail-link {
    overflow: hidden;
    padding: var(--space-3) var(--space-2);
    font-size: 0.75rem;
    text-align: center;
  }

  .pane-header {
    padding: var(--space-4);
  }

  .pane-content {
    padding: var(--space-4);
  }
}
</style>
