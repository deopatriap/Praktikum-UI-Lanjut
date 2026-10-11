<script setup>
const events = [
  {
    id: 1,
    title: 'Vue.js Mastery Workshop',
    date: 'Oct 12, 2026',
    loc: '📍 Tech Hub, Jakarta',
    cat: 'Workshop',
    desc: 'Learn advanced Vue 3 concepts, Composition API, and state management to build high-performance web applications interactively.',
  },
  {
    id: 2,
    title: 'National Tech Meetup',
    date: 'Oct 15, 2026',
    loc: '📍 Main Auditorium, City Center',
    cat: 'Meetup',
    desc: 'A gathering of hundreds of developers and tech enthusiasts to share the latest industry trends and expand professional networks.',
  },
  {
    id: 3,
    title: 'Startup Pitch Competition',
    date: 'Nov 02, 2026',
    loc: '📍 Innovation Center',
    cat: 'Competition',
    desc: 'Watch the best local startup founders pitch their innovative ideas live in front of a panel of renowned investors.',
  },
  {
    id: 4,
    title: 'UI/UX Design Sprint',
    date: 'Nov 10, 2026',
    loc: '📍 Creative Studio',
    cat: 'Workshop',
    desc: 'A hands-on session on designing user interfaces by implementing layout systems and visual hierarchy principles.',
  },
  {
    id: 5,
    title: 'Digital Marketing Seminar',
    date: 'Nov 20, 2026',
    loc: '📍 Grand Hotel Hall',
    cat: 'Seminar',
    desc: 'An in-depth seminar exploring modern strategies, from SEO optimization to user conversion tactics.',
  },
  {
    id: 6,
    title: 'Community Leaders Summit',
    date: 'Dec 05, 2026',
    loc: '📍 Gatherly HQ',
    cat: 'Conference',
    desc: 'An exclusive year-end conference for community leaders to formulate sustainable ecosystem development strategies.',
  },
]
</script>

<template>
  <div class="event-list-page">
    <div class="header-section">
      <h2 class="section-title">Upcoming Events</h2>
      <p class="section-desc">
        Discover workshops, seminars, tech meetups, and competitions near you.
      </p>
    </div>

    <div class="event-grid">
      <article v-for="event in events" :key="event.id" class="event-card">
        <div class="event-body">
          <div class="event-meta">
            <span class="event-date">{{ event.date }}</span>
            <span class="event-category">{{ event.cat }}</span>
          </div>
          <h3 class="event-title">{{ event.title }}</h3>
          <p class="event-loc">{{ event.loc }}</p>
          <p class="event-desc">{{ event.desc }}</p>
          <div class="card-footer">
            <RouterLink :to="`/browse/events/${event.id}`" class="btn-link">
              View Event Details &rarr;
            </RouterLink>
          </div>
        </div>
      </article>
    </div>
  </div>
</template>

<style scoped>
.event-list-page {
  animation: fadeIn 0.5s ease;
}

.header-section {
  margin-bottom: var(--space-8);
}

.section-title {
  margin: 0 0 var(--space-2);
  color: var(--text-main);
  font-size: 2rem;
}

.section-desc {
  margin: 0;
  color: var(--text-muted);
  font-size: 1.05rem;
}

.event-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 320px), 1fr));
  gap: var(--space-6);
}

.event-card {
  border: 1px solid var(--border-color);
  border-radius: var(--space-4);
  box-shadow: 0 4px 15px rgb(0 0 0 / 2%);
}

.event-body {
  height: 100%;
  padding: var(--space-6);
  display: flex;
  flex-direction: column;
}

.event-meta {
  display: flex;
  justify-content: space-between;
  gap: var(--space-2);
  margin-bottom: var(--space-4);
}

.event-date,
.event-category {
  color: var(--primary);
  font-size: 0.85rem;
  font-weight: 600;
}

.event-title {
  margin: 0 0 var(--space-2);
  color: var(--text-main);
  font-size: 1.3rem;
}

.event-loc,
.event-desc {
  color: var(--text-muted);
  font-size: 0.95rem;
}

.event-desc {
  flex: 1;
}

.card-footer {
  margin-top: var(--space-4);
  padding-top: var(--space-4);
  border-top: 1px solid var(--border-color);
}

.btn-link {
  color: var(--primary);
  font-weight: 600;
  text-decoration: none;
}

.btn-link:hover {
  text-decoration: underline;
}

@media (max-width: 480px) {
  .event-meta {
    flex-wrap: wrap;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
