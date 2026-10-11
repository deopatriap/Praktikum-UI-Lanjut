<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import { useRoute } from 'vue-router'

const isScrolled = ref(false)
const route = useRoute()

const menus = [
  { name: 'Home', path: '/' },
  { name: 'About', path: '/about' },
  {
    name: 'Browse',
    path: '/browse',
    children: [
      {
        name: 'Event List',
        path: '/browse/events',
        children: [{ name: 'Event Detail (Sample)', path: '/browse/events/1' }],
      },
      { name: 'Category', path: '/browse/category' },
    ],
  },
  { name: 'Contact', path: '/contact' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 10
}

onMounted(() => window.addEventListener('scroll', handleScroll))
onUnmounted(() => window.removeEventListener('scroll', handleScroll))
</script>

<template>
  <nav class="navbar" :class="{ scrolled: isScrolled }">
    <div class="navbar-container">
      <RouterLink to="/" class="logo">
        <svg
          width="28"
          height="32"
          viewBox="0 0 24 28"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
          class="logo-icon"
        >
          <path d="M12 0L22.3923 6V18L12 24L1.6077 18V6L12 0Z" fill="white" />
          <path
            d="M15 9.5 C15 9.5 14 8 12 8 C9.5 8 8 10 8 12.5 C8 15 9.5 17 12 17 C14 17 15 16 15.5 14.5 V 12.5 H 12.5"
            stroke="#1A1643"
            stroke-width="2.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          />
        </svg>
        <span class="logo-text">Gatherly</span>
      </RouterLink>

      <ul class="nav-menu">
        <li v-for="menu in menus" :key="menu.name" class="nav-item">
          <RouterLink
            :to="menu.path"
            class="nav-link"
            :class="{
              active:
                route.path === menu.path || (menu.path !== '/' && route.path.startsWith(menu.path)),
            }"
          >
            {{ menu.name }}
            <svg
              v-if="menu.children"
              class="dropdown-indicator"
              width="12"
              height="12"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
              stroke-linejoin="round"
            >
              <polyline points="6 9 12 15 18 9"></polyline>
            </svg>
          </RouterLink>

          <ul v-if="menu.children" class="dropdown-menu">
            <li v-for="child in menu.children" :key="child.name" class="dropdown-item">
              <RouterLink :to="child.path" class="dropdown-link">
                {{ child.name }}
                <svg
                  v-if="child.children"
                  class="submenu-indicator"
                  width="12"
                  height="12"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <polyline points="9 18 15 12 9 6"></polyline>
                </svg>
              </RouterLink>
              <ul v-if="child.children" class="submenu">
                <li v-for="subchild in child.children" :key="subchild.name" class="submenu-item">
                  <RouterLink :to="subchild.path" class="dropdown-link">
                    {{ subchild.name }}
                  </RouterLink>
                </li>
              </ul>
            </li>
          </ul>
        </li>
      </ul>

      <div class="nav-right">
        <div class="lang-selector">
          <svg
            width="20"
            height="20"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <circle cx="12" cy="12" r="10"></circle>
            <line x1="2" y1="12" x2="22" y2="12"></line>
            <path
              d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"
            ></path>
          </svg>
          <span class="lang-text">EN</span>
          <svg
            width="18"
            height="18"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="chevron"
          >
            <polyline points="6 9 12 15 18 9"></polyline>
          </svg>
        </div>
        <button class="hamburger-btn" type="button" aria-label="Toggle navigation">
          <svg
            width="24"
            height="24"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="1.5"
            stroke-linecap="round"
            stroke-linejoin="round"
          >
            <line x1="4" y1="12" x2="20" y2="12"></line>
            <line x1="4" y1="6" x2="20" y2="6"></line>
            <line x1="4" y1="18" x2="20" y2="18"></line>
          </svg>
        </button>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  width: 100%;
  background: var(--nav-bg, #1c1948);
  border-bottom: 1px solid var(--nav-border, #333);
  box-shadow: 0 4px 20px rgb(0 0 0 / 15%);
  position: sticky;
  top: 0;
  z-index: 999;
  transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
}

.navbar-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 100%;
  max-width: 1440px;
  margin: 0 auto;
  padding: 0.85rem 2rem;
}

.navbar.scrolled {
  background: rgba(28, 25, 72, 0.9);
  backdrop-filter: blur(12px);
}

.logo {
  display: flex;
  align-items: center;
  gap: 0.75rem;
  text-decoration: none;
}

.logo-text {
  color: white;
  font-size: 1.4rem;
  font-weight: 800;
  letter-spacing: -0.5px;
}

.logo-icon {
  filter: drop-shadow(0 2px 4px rgb(0 0 0 / 20%));
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 2.5rem;
  flex: 1;
  justify-content: center;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-item {
  position: relative;
  display: flex;
  align-items: center;
  height: 100%;
  padding: 1rem 0;
}

.nav-link {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  text-decoration: none;
  color: var(--text-white, #fff);
  font-size: 0.95rem;
  font-weight: 500;
  padding: 0.5rem 1.25rem;
  border-radius: 10px;
  transition: all 0.3s ease;
}

.nav-link:hover,
.nav-link.active {
  background: rgb(255 255 255 / 10%);
  color: white;
}

.dropdown-menu,
.submenu {
  display: none;
  position: absolute;
  background-color: #d8d8d8;
  min-width: 220px;
  list-style: none;
  padding: 0;
  margin: 0;
  box-shadow: 0 8px 16px rgb(0 0 0 / 20%);
  border-radius: 4px;
}

.dropdown-menu {
  top: 100%;
  left: 0;
}

.nav-item:hover > .dropdown-menu {
  display: block;
  animation: fadeIn 0.2s ease-out;
}

.dropdown-item {
  position: relative;
}

.dropdown-link {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 16px;
  color: #333;
  text-decoration: none;
  white-space: nowrap;
  transition: background-color 0.2s;
}

.dropdown-link:hover {
  background-color: #c0c0c0;
}

.submenu {
  top: 0;
  left: 100%;
}

.dropdown-item:hover > .submenu {
  display: block;
  animation: fadeIn 0.2s ease-out;
}

.nav-right {
  display: flex;
  align-items: center;
  gap: 1.5rem;
}

.lang-selector {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: white;
}

.hamburger-btn {
  display: none;
  color: white;
  background: none;
  border: 0;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(-5px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 900px) {
  .nav-menu {
    gap: 0.5rem;
  }

  .nav-link {
    padding: 0.5rem 0.75rem;
  }
}

@media (max-width: 700px) {
  .navbar-container {
    padding: 0.85rem 1rem;
  }

  .nav-menu {
    display: none;
  }

  .hamburger-btn {
    display: block;
  }
}
</style>
