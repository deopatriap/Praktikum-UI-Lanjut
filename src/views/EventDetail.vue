<template>
  <div class="event-detail-page">
    <button @click="$router.push('/browse/events')" class="btn-back">&larr; Back to Events</button>

    <div class="detail-header">
      <div class="header-content">
        <span class="event-tag">Community Event</span>
        <h1>Community Gathering {{ $route.params.id }}</h1>
        <div class="meta-info">
          <div class="meta-item">
            <span class="icon">📅</span>
            <span>October 15, 2026</span>
          </div>
          <div class="meta-item">
            <span class="icon">📍</span>
            <span>Main Auditorium, City Center</span>
          </div>
          <div class="meta-item">
            <span class="icon">👥</span>
            <span>500+ Attendees</span>
          </div>
        </div>
      </div>
    </div>

    <div class="detail-content">
      <div class="main-desc">
        <h2>About This Event</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in dui mauris. Vivamus
          hendrerit arcu sed erat molestie vehicula. Sed auctor neque eu tellus rhoncus ut eleifend
          nibh porttitor. Ut in nulla enim. Phasellus molestie magna non est bibendum non venenatis
          nisl tempor.
        </p>
        <p>
          Suspendisse dictum feugiat nisl ut dapibus. Mauris lacus felis, porttitor id metus massa,
          ut blandit odio. Proin quis tortor orci. Etiam at risus et justo dignissim congue. Donec
          congue lacinia dui, a porttitor lectus condimentum laoreet. Nunc eu ullamcorper orci.
        </p>

        <h2>Agenda</h2>
        <ul class="agenda-list">
          <li><strong>09:00 AM</strong> Registration &amp; Welcome Coffee</li>
          <li><strong>10:00 AM</strong> Opening Keynote Speech</li>
          <li><strong>11:30 AM</strong> Networking Session</li>
          <li><strong>01:00 PM</strong> Closing Remarks &amp; Lunch</li>
        </ul>
      </div>

      <div class="sidebar">
        <div class="ticket-card">
          <h3>Registration</h3>
          <p class="price">Free</p>
          <p class="ticket-desc">Secure your spot today before it runs out.</p>
          <button class="btn-register">Register Now</button>
          <p class="spots">Only 45 spots left!</p>
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
  margin-bottom: 1.5rem;
  padding: 0.6rem 1rem;
  color: #6644cc;
  background: transparent;
  border: 0;
  cursor: pointer;
  font-size: 1rem;
}

.detail-header {
  padding: 3rem;
  color: white;
  background: linear-gradient(135deg, #6644cc, #8e66ff);
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
  display: flex;
  gap: 3rem;
  margin-top: 3rem;
}

.main-desc {
  flex: 2;
}

.main-desc h2 {
  color: #1c1948;
  margin: 0 0 1rem;
}

.main-desc p {
  color: #666;
  line-height: 1.8;
  margin-bottom: 1.5rem;
}

.agenda-list {
  list-style: none;
  padding: 0;
}

.agenda-list li {
  padding: 1rem 0;
  border-bottom: 1px solid #f0f0f0;
  color: #444;
}

.agenda-list strong {
  display: inline-block;
  width: 100px;
  color: #6644cc;
}

.sidebar {
  flex: 1;
}

.ticket-card {
  position: sticky;
  top: 100px;
  padding: 2.5rem;
  background: white;
  border: 1px solid #f0f0f0;
  border-radius: 16px;
  box-shadow: 0 4px 20px rgb(0 0 0 / 2%);
  text-align: center;
}

.ticket-card h3 {
  margin: 0;
  color: #1c1948;
}

.price {
  margin: 0.8rem 0;
  color: #6644cc;
  font-size: 2rem;
  font-weight: 700;
}

.ticket-desc,
.spots {
  color: #666;
}

.btn-register {
  width: 100%;
  padding: 0.8rem 1rem;
  color: white;
  background: #6644cc;
  border: 0;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 600;
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
    flex-direction: column;
  }

  .detail-header {
    padding: 2rem;
  }
}
</style>
