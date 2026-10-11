<template>
  <div class="event-list-page">
    <div class="header-section">
      <h2 class="section-title">Upcoming Events</h2>
      <p class="section-desc">Discover the latest gatherings and activities happening near you.</p>
    </div>

    <div class="event-grid">
      <div v-for="i in 6" :key="i" class="event-card">
        <div class="event-body">
          <div class="event-meta">
            <span class="event-date">Oct {{ 10 + i }}, 2026</span>
            <span class="event-category">Community</span>
          </div>
          <h3>Community Gathering {{ i }}</h3>
          <p class="event-loc">⌖ Main Auditorium, City Center</p>
          <p class="event-desc">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam at velit vel magna
            interdum scelerisque.
          </p>
          <div class="card-footer">
            <RouterLink :to="`/browse/events/${i}`" class="btn-link">
              View Details &rarr;
            </RouterLink>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.event-list-page {
  animation: fadeIn 0.5s ease;
}

.header-section {
  margin-bottom: 2rem;
}

.section-title {
  margin: 0 0 0.5rem;
  color: #1c1948;
  font-size: 2rem;
}

.section-desc {
  margin: 0;
  color: #666;
  font-size: 1.05rem;
}

.event-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.event-card {
  overflow: hidden;
  background: white;
  border: 1px solid #f0f0f0;
  border-radius: 16px;
  box-shadow: 0 4px 15px rgb(0 0 0 / 2%);
}

.event-body {
  padding: 1.5rem;
}

.event-meta {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
}

.event-date,
.event-category {
  color: #6644cc;
  font-size: 0.85rem;
  font-weight: 600;
}

.event-card h3 {
  margin: 0 0 0.7rem;
  color: #1c1948;
  font-size: 1.3rem;
}

.event-loc,
.event-desc {
  color: #666;
  font-size: 0.95rem;
}

.event-desc {
  line-height: 1.6;
}

.card-footer {
  margin-top: 1.5rem;
  padding-top: 1rem;
  border-top: 1px solid #f0f0f0;
}

.btn-link {
  color: #6644cc;
  font-weight: 600;
  text-decoration: none;
}

.btn-link:hover {
  text-decoration: underline;
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
