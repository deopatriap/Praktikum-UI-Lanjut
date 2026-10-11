<template>
  <div class="home-page">
    <section class="hero">
      <div class="hero-content">
        <span class="badge">Welcome to Gatherly</span>
        <h1 class="hero-title">Connect, Discover, and Experience</h1>
        <p class="hero-subtitle">
          Join our vibrant community to explore the best events tailored for you. Lorem ipsum dolor
          sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et
          dolore magna aliqua.
        </p>
        <div class="hero-actions">
          <RouterLink to="/browse/events" class="btn btn-primary">Discover Events</RouterLink>
          <RouterLink to="/about" class="btn btn-secondary">Learn More</RouterLink>
        </div>
      </div>
    </section>

    <section class="features">
      <div v-for="i in 3" :key="i" class="feature-card">
        <div class="feature-icon">{{ ['🎉', '🌍', '🤝'][i - 1] }}</div>
        <h3>{{ ['Curated Events', 'Global Reach', 'Community Driven'][i - 1] }}</h3>
        <p>
          Et enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
          commodo consequat.
        </p>
      </div>
    </section>

    <section class="sitemap-visual">
      <h2>Website Structure / Site-Map</h2>
      <p class="sitemap-desc">
        A quick overview of how this application is structured via Vue Router.
      </p>
      <ul class="tree">
        <li><RouterLink to="/">Home</RouterLink></li>
        <li><RouterLink to="/about">About</RouterLink></li>
        <li>
          <RouterLink to="/browse">Browse</RouterLink>
          <ul>
            <li>
              <RouterLink to="/browse/events">Event List</RouterLink>
              <ul>
                <li><RouterLink to="/browse/events/1">Event Detail</RouterLink></li>
              </ul>
            </li>
            <li><RouterLink to="/browse/category">Category</RouterLink></li>
          </ul>
        </li>
        <li><RouterLink to="/contact">Contact</RouterLink></li>
      </ul>
    </section>
  </div>
</template>

<style scoped>
.home-page {
  display: flex;
  flex-direction: column;
  gap: 4rem;
  animation: fadeIn 0.5s ease;
}

.hero {
  display: flex;
  justify-content: center;
  padding: 5rem 2rem;
  background: #fdfdfd;
  border: 1px solid #f0f0f0;
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

.badge {
  display: inline-block;
  margin-bottom: 2rem;
  padding: 0.5rem 1.2rem;
  color: #6644ff;
  background: rgb(102 68 255 / 8%);
  border-radius: 50px;
  font-size: 0.9rem;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.hero-title {
  margin: 0 0 1.5rem;
  color: #1c1948;
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.2;
}

.hero-subtitle {
  max-width: 700px;
  margin: 0 auto;
  color: #666;
  font-size: 1.15rem;
  line-height: 1.7;
}

.hero-actions {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
  margin-top: 2rem;
}

.btn {
  display: inline-flex;
  justify-content: center;
  padding: 0.75rem 1.5rem;
  color: #1c1948;
  text-decoration: none;
  border: 1px solid transparent;
  border-radius: 10px;
  font-weight: 700;
  transition:
    background-color 160ms ease,
    transform 160ms ease,
    box-shadow 160ms ease;
}

.btn:hover {
  transform: translateY(-2px);
}

.btn-primary {
  background: #6644ff;
  color: white;
  box-shadow: 0 4px 15px rgb(102 68 255 / 20%);
}

.btn-primary:hover {
  background: #5533ee;
  transform: translateY(-2px);
}

.btn-secondary {
  color: #1c1948;
  background: white;
  border: 1px solid #e0e0e0;
}

.btn-secondary:hover {
  border-color: #6644ff;
  color: #6644ff;
  transform: translateY(-2px);
}

.features {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.feature-card {
  background: white;
  padding: 2.5rem;
  border-radius: 18px;
  border: 1px solid #f0f0f0;
  box-shadow: 0 4px 15px rgb(0 0 0 / 2%);
  transition: all 0.3s ease;
  text-align: center;
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgb(0 0 0 / 5%);
  border-color: #e0e0e0;
}

.feature-icon {
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
}

.feature-card h3 {
  margin: 0 0 0.7rem;
  color: #1c1948;
  font-size: 1.2rem;
  font-weight: 700;
}

.feature-card p {
  margin: 0;
  color: #666;
  line-height: 1.7;
}

.sitemap-visual {
  padding: 3rem;
  background: #fafafa;
  border-radius: 16px;
  border: 1px solid #f0f0f0;
}

.sitemap-visual h2 {
  color: #1c1948;
  margin-bottom: 0.5rem;
}

.sitemap-desc {
  color: #666;
  margin-bottom: 2.5rem;
}

.tree,
.tree ul {
  list-style: none;
  padding-left: 20px;
}

.tree li {
  margin: 12px 0;
  position: relative;
}

.tree li::before {
  content: '';
  position: absolute;
  top: -12px;
  left: -15px;
  border-left: 1px solid #ddd;
  border-bottom: 1px solid #ddd;
  width: 10px;
  height: 30px;
}

.tree a {
  color: #333;
  text-decoration: none;
}

.tree a:hover {
  color: #6644cc;
  text-decoration: underline;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0px);
  }
}
</style>
