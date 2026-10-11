<template>
  <div class="about-page">
    <div class="about-header">
      <h1>About Gatherly</h1>
      <p>Building the future of event experiences, one community at a time.</p>
    </div>

    <div class="about-content">
      <div class="text-block">
        <h2>Our Mission</h2>
        <p>
          Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat
          nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia
          deserunt mollit anim id est laborum. Sed ut perspiciatis unde omnis iste natus error sit
          voluptatem accusantium doloremque laudantium.
        </p>
      </div>

      <div class="text-block">
        <h2>Our Vision</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer nec odio. Praesent
          libero. Sed cursus ante dapibus diam. Sed nisi. Nulla quis sem at nibh elementum
          imperdiet. Duis sagittis ipsum. Praesent mauris. Fusce nec tellus sed augue semper porta.
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-page {
  animation: fadeIn 0.5s ease;
}

.about-header {
  margin-bottom: 3rem;
  text-align: center;
}

.about-header h1 {
  margin-bottom: 1rem;
  color: #1c1948;
  font-size: 2.8rem;
}

.about-header p {
  color: #666;
  font-size: 1.1rem;
}

.about-content {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
}

.text-block {
  padding: 2rem;
  background: #fff;
  border: 1px solid #f0f0f0;
  border-radius: 16px;
}

.text-block h2 {
  color: #1c1948;
  margin-bottom: 1rem;
}

.text-block p {
  color: #666;
  line-height: 1.8;
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
