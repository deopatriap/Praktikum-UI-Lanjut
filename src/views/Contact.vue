<template>
  <div class="contact-page">
    <div class="contact-header">
      <h1>Contact Us</h1>
      <p>
        We'd love to hear from you. Please fill out the form below or reach out via our contact
        info.
      </p>
    </div>

    <div class="contact-content">
      <div class="contact-info">
        <div class="info-item">
          <div class="icon-info">📍</div>
          <div>
            <h3>Our Office</h3>
            <p>123 Event Street, Tech City, 10101</p>
          </div>
        </div>
        <div class="info-item">
          <div class="icon-info">📞</div>
          <div>
            <h3>Phone</h3>
            <p>+62 812 3456 7890</p>
          </div>
        </div>
        <div class="info-item">
          <div class="icon-info">✉️</div>
          <div>
            <h3>Email</h3>
            <p>hello@gatherly.com</p>
          </div>
        </div>
      </div>

      <div class="contact-form">
        <form @submit.prevent>
          <div class="form-group">
            <label>Name</label>
            <input type="text" placeholder="John Doe" class="form-control" />
          </div>
          <div class="form-group">
            <label>Email</label>
            <input type="email" placeholder="john@example.com" class="form-control" />
          </div>
          <div class="form-group">
            <label>Message</label>
            <textarea rows="5" placeholder="How can we help?" class="form-control"></textarea>
          </div>
          <button type="submit" class="btn-submit">Send Message</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact-page {
  animation: fadeIn 0.5s ease;
}

.contact-header {
  text-align: center;
  margin-bottom: 4rem;
}

.contact-header h1 {
  font-size: 2.8rem;
  color: #1c1948;
  margin-bottom: 1rem;
}

.contact-header p {
  font-size: 1.1rem;
  color: #666;
}

.contact-content {
  display: flex;
  gap: 4rem;
  max-width: 1000px;
  margin: 0 auto;
}

.contact-info {
  flex: 1;
}

.info-item {
  display: flex;
  gap: 1rem;
  margin-bottom: 2rem;
}

.icon-info {
  display: grid;
  width: 50px;
  height: 50px;
  flex: none;
  place-items: center;
  color: #6644cc;
  background: #f4f1ff;
  border-radius: 12px;
  font-size: 1.4rem;
}

.info-item h3 {
  margin: 0 0 0.5rem;
  color: #1c1948;
}

.info-item p {
  margin: 0;
  color: #666;
}

.contact-form {
  flex: 1.5;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: #1c1948;
  font-weight: 600;
}

.form-control {
  width: 100%;
  padding: 0.8rem 1rem;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  font: inherit;
}

.form-control:focus {
  border-color: #6644cc;
  outline: none;
}

.btn-submit {
  width: 100%;
  padding: 0.8rem;
  color: white;
  background: #6644cc;
  border: 0;
  border-radius: 8px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 600;
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
  .contact-content {
    flex-direction: column;
    gap: 2rem;
  }
}
</style>
