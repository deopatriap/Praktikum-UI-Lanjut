<template>
  <div class="category-page">
    <h2 class="section-title">Explore by Category</h2>
    <div class="category-grid">
      <RouterLink to="/browse/events" class="category-card">
        <span class="category-icon">🎨</span>
        <h3>Arts &amp; Culture</h3>
      </RouterLink>
      <RouterLink to="/browse/events" class="category-card">
        <span class="category-icon">💻</span>
        <h3>Technology</h3>
      </RouterLink>
      <RouterLink to="/browse/events" class="category-card">
        <span class="category-icon">🎵</span>
        <h3>Music</h3>
      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
.category-page {
  animation: fadeIn 0.5s ease;
}

.section-title {
  margin-bottom: 2rem;
  color: #1c1948;
  font-size: 2rem;
}

.category-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.category-card {
  display: flex;
  align-items: center;
  gap: 1rem;
  padding: 1.5rem;
  color: #1c1948;
  background: white;
  border: 1px solid #f0f0f0;
  border-radius: 16px;
  text-decoration: none;
  transition: transform 0.2s ease;
}

.category-card:hover {
  transform: translateY(-5px);
}

.category-icon {
  font-size: 2rem;
}

.category-card h3 {
  margin: 0;
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
