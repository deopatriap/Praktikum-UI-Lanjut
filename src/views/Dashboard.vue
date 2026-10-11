<script setup>
const registrations = [
  {
    name: 'John Doe',
    event: 'Vue.js Mastery Workshop',
    date: 'Oct 12, 2026',
    status: 'Confirmed',
  },
  {
    name: 'Jane Smith',
    event: 'National Tech Meetup',
    date: 'Oct 15, 2026',
    status: 'Confirmed',
  },
  {
    name: 'Alex Johnson',
    event: 'Startup Pitch Competition',
    date: 'Nov 02, 2026',
    status: 'Pending',
  },
  {
    name: 'Taylor Brown',
    event: 'UI/UX Design Sprint',
    date: 'Nov 10, 2026',
    status: 'Confirmed',
  },
  {
    name: 'Morgan Lee',
    event: 'Digital Marketing Seminar',
    date: 'Nov 20, 2026',
    status: 'Confirmed',
  },
]
</script>

<template>
  <div class="dashboard-overview">
    <h2>Welcome back, Organizer</h2>

    <div class="metrics-grid">
      <article class="metric-card">
        <h3>Total Tickets Sold</h3>
        <p class="metric-value">1,245</p>
      </article>
      <article class="metric-card">
        <h3>Page Views</h3>
        <p class="metric-value">8,302</p>
      </article>
      <article class="metric-card">
        <h3>Revenue</h3>
        <p class="metric-value">$12,450</p>
      </article>
    </div>

    <section class="data-table-container">
      <h3>Recent Registrations</h3>
      <div class="table-scroll">
        <table class="data-table">
          <thead>
            <tr>
              <th>Attendee Name</th>
              <th>Event</th>
              <th>Registration Date</th>
              <th>Status</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="registration in registrations" :key="registration.name">
              <td>{{ registration.name }}</td>
              <td>{{ registration.event }}</td>
              <td>{{ registration.date }}</td>
              <td>
                <span class="status-badge" :class="registration.status.toLowerCase()">
                  {{ registration.status }}
                </span>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>
  </div>
</template>

<style scoped>
.dashboard-overview h2 {
  margin: 0 0 var(--space-6);
  color: var(--text-main);
}

.metrics-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(min(100%, 220px), 1fr));
  gap: var(--space-6);
  margin-bottom: var(--space-8);
}

.metric-card {
  padding: var(--space-6);
  background: white;
  border: 1px solid var(--border-color);
  border-radius: var(--space-2);
  box-shadow: 0 2px 8px rgb(0 0 0 / 3%);
}

.metric-card h3 {
  margin: 0;
  color: var(--text-muted);
  font-size: 0.95rem;
  font-weight: 500;
}

.metric-value {
  margin: var(--space-2) 0 0;
  color: var(--text-main);
  font-size: 1.8rem;
  font-weight: 700;
}

.data-table-container {
  padding: var(--space-6);
  background: white;
  border: 1px solid var(--border-color);
  border-radius: var(--space-2);
}

.data-table-container h3 {
  margin: 0 0 var(--space-4);
  color: var(--text-main);
}

.table-scroll {
  overflow-x: auto;
}

.data-table {
  width: 100%;
  border-collapse: collapse;
  text-align: left;
}

.data-table th,
.data-table td {
  padding: var(--space-3) var(--space-4);
  border-bottom: 1px solid var(--border-color);
  white-space: nowrap;
}

.data-table th {
  color: var(--text-muted);
  font-size: 0.85rem;
  font-weight: 600;
}

.data-table td {
  color: var(--text-main);
}

.data-table tbody tr:last-child td {
  border-bottom: 0;
}

.status-badge {
  display: inline-block;
  padding: var(--space-1) var(--space-2);
  color: #166534;
  background: #dcfce7;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 600;
}

.status-badge.pending {
  color: #854d0e;
  background: #fef9c3;
}
</style>
