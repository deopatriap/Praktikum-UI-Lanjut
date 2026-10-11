<template>
  <div class="event-detail-page">
    <button @click="$router.push('/browse/events')" class="btn-back">&larr; Back to Events</button>

    <div class="detail-header">
      <div class="header-content">
        <span class="event-tag">Workshop &amp; Training</span>
        <h1>Vue.js Mastery Workshop {{ $route.params.id }}</h1>
        <div class="meta-info">
          <div class="meta-item">
            <span class="icon">📅</span>
            <span>October 12, 2026</span>
          </div>
          <div class="meta-item">
            <span class="icon">📍</span>
            <span>Tech Hub, Jakarta</span>
          </div>
          <div class="meta-item">
            <span class="icon">👥</span>
            <span>Quota: 150 Attendees</span>
          </div>
        </div>
      </div>
    </div>

    <div class="detail-content">
      <div class="main-desc">
        <h2>About This Event</h2>
        <p>
          Welcome to the biggest web interface development training event of the year! Gatherly is
          collaborating with the local developer community to host a comprehensive workshop designed
          specifically to bring together professionals, enthusiasts, and students.
        </p>
        <p>
          In this session, we will discuss various current industry challenges, dissect the
          implementation of Single Page Applications (SPA), and practice hands-on Layout System
          design prioritizing visual hierarchy. You will gain practical insights that can be
          directly applied to your future projects or career.
        </p>

        <h2>Event Agenda</h2>
        <ul class="agenda-list">
          <li><strong>09:00 AM</strong> Registration &amp; QR Check-in Scanning</li>
          <li><strong>10:00 AM</strong> Session 1: Vue Router &amp; Navigation Fundamentals</li>
          <li><strong>11:30 AM</strong> Coffee Break &amp; Networking Session</li>
          <li><strong>01:00 PM</strong> Session 2: Layout System &amp; Grid Implementation</li>
          <li><strong>03:00 PM</strong> Q&amp;A &amp; Closing Remarks</li>
        </ul>
      </div>

      <div class="sidebar">
        <div class="ticket-card sticky-pane">
          <h3>Attendee Registration</h3>
          <p class="price">Free</p>
          <p class="ticket-desc">Secure your seat now before the quota is full.</p>
          <button class="btn-register">Register Now</button>
          <p class="spots">Only 12 seats left!</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.event-detail-page {
  animation: fadeIn 0.5s ease;
}

.btn-back {
  margin-bottom: var(--space-6);
  padding: var(--space-2) var(--space-4);
  color: var(--primary);
  background: transparent;
  border: 0;
  cursor: pointer;
  font-size: 1rem;
}

.detail-header {
  padding: 3rem;
  color: white;
  background: linear-gradient(135deg, var(--primary), #8e66ff);
  border-radius: 20px;
}

.header-content {
  max-width: 800px;
}

.event-tag {
  display: inline-block;
  margin-bottom: 1rem;
  padding: 0.4rem 1rem;
  background: rgb(255 255 255 / 20%);
  border-radius: 50px;
  font-size: 0.9rem;
}

.detail-header h1 {
  margin: 0 0 1.5rem;
  font-size: 2.8rem;
  line-height: 1.15;
}

.meta-info {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
}

.meta-item {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.detail-content {
  display: grid;
  grid-template-columns: minmax(0, 2fr) minmax(250px, 1fr);
  gap: var(--space-12);
  margin-top: 3rem;
}

.main-desc h2 {
  color: var(--text-main);
  margin: 0 0 1rem;
}

.main-desc p {
  color: var(--text-muted);
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.agenda-list {
  padding-left: var(--space-6);
}

.agenda-list li {
  padding: var(--space-4) 0;
  border-bottom: 1px solid var(--border-color);
  color: #444;
}

.agenda-list strong {
  display: inline-block;
  min-width: 100px;
  color: var(--primary);
}

.ticket-card {
  position: relative;
  padding: 2.5rem;
  background: white;
  border: 1px solid var(--border-color);
  border-radius: 16px;
  box-shadow: 0 4px 20px rgb(0 0 0 / 2%);
  text-align: center;
}

.sticky-pane {
  position: sticky;
  top: 100px;
}

.ticket-card h3 {
  margin: 0;
  color: var(--text-main);
}

.price {
  margin: 0.8rem 0;
  color: var(--primary);
  font-size: 2rem;
  font-weight: 700;
}

.ticket-desc,
.spots {
  color: var(--text-muted);
}

.btn-register {
  width: 100%;
  padding: var(--space-3) var(--space-4);
  color: white;
  background: var(--primary);
  border: 0;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 600;
}

.btn-register:hover {
  background: var(--primary-hover);
}

.spots {
  margin-bottom: 0;
  font-size: 0.85rem;
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

@media (max-width: 760px) {
  .detail-content {
    grid-template-columns: 1fr;
    gap: var(--space-8);
  }

  .detail-header {
    padding: 2rem;
  }

  .detail-header h1 {
    font-size: 2.2rem;
  }

  .sticky-pane {
    position: static;
  }
}
</style>
