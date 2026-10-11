<template>
  <div class="home-page">
    <section class="hero-section">
      <div class="hero-content">
        <h1 class="hero-title">Connect, Discover, and Experience</h1>
        <p class="hero-subtitle">
          A community event platform designed to bring ideas together. Discover hundreds of events
          near you.
        </p>
        <div class="hero-actions">
          <RouterLink to="/browse/events" class="btn btn-primary">Discover Events</RouterLink>
        </div>
      </div>
    </section>

    <section class="features-section">
      <div class="features-header">
        <h2>Why Choose Gatherly?</h2>
        <p>Everything you need to host or attend unforgettable events.</p>
      </div>

      <div class="features-grid">
        <article class="feature-card">
          <div class="feature-icon" aria-hidden="true">🔎</div>
          <h3>Discover Easily</h3>
          <p>Find events tailored to your interests using smart category and location filters.</p>
        </article>
        <article class="feature-card">
          <div class="feature-icon" aria-hidden="true">🎟️</div>
          <h3>Seamless Ticketing</h3>
          <p>Register with one click and get your digital QR ticket instantly on your device.</p>
        </article>
        <article class="feature-card">
          <div class="feature-icon" aria-hidden="true">📊</div>
          <h3>Host Like a Pro</h3>
          <p>
            Manage attendees, track revenue, and scan QR codes with our comprehensive dashboard.
          </p>
        </article>
      </div>
    </section>
  </div>
</template>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  gap: var(--space-12);
}

.hero-section {
  display: flex;
  justify-content: center;
  min-height: 65vh;
  align-items: center;
  padding: var(--space-8) var(--space-4);
  background: var(--bg-light);
  border: 1px solid var(--border-color);
  border-radius: 24px;
  box-shadow: 0 4px 20px rgb(0 0 0 / 2%);
  text-align: center;
}

.hero-content {
  display: flex;
  max-width: 800px;
  flex-direction: column;
  align-items: center;
}

.hero-title {
  margin: 0 0 var(--space-6);
  color: var(--text-main);
  font-size: clamp(2.5rem, 6vw, 4rem);
  font-weight: 800;
  line-height: 1.1;
}

.hero-subtitle {
  max-width: 600px;
  margin: 0 0 var(--space-8);
  color: var(--text-muted);
  font-size: 1.25rem;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: var(--space-4);
}

.btn {
  display: inline-flex;
  justify-content: center;
  padding: var(--space-3) var(--space-8);
  border: 0;
  border-radius: 12px;
  font-size: 1.1rem;
  font-weight: 600;
  text-decoration: none;
  transition:
    transform 0.2s,
    background-color 0.2s;
}

.btn-primary {
  color: white;
  background: var(--primary);
  box-shadow: 0 4px 15px rgb(102 68 255 / 20%);
}

.btn-primary:hover {
  transform: translateY(-2px);
  background: var(--primary-hover);
}

.features-header {
  margin-bottom: var(--space-8);
  text-align: center;
}

.features-header h2 {
  margin: 0 0 var(--space-2);
  color: var(--text-main);
  font-size: 1.75rem;
}

.features-header p {
  margin: 0;
  color: var(--text-muted);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 280px), 1fr));
  gap: var(--space-8);
}

.feature-card {
  padding: var(--space-8);
  background: white;
  border: 1px solid var(--border-color);
  border-radius: 18px;
  box-shadow: 0 4px 15px rgb(0 0 0 / 2%);
  text-align: center;
  transition:
    transform 0.3s ease,
    box-shadow 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgb(0 0 0 / 5%);
}

.feature-icon {
  font-size: 2.5rem;
  margin-bottom: var(--space-6);
}

.feature-card h3 {
  margin: 0 0 var(--space-2);
  color: var(--text-main);
}

.feature-card p {
  margin: 0;
  color: var(--text-muted);
}
</style>
