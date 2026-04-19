<script setup lang="ts">
import { ref } from 'vue'
import type { Product } from '../Interfaces/Products';
const isMenuOpen = ref(false)
const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <header class="store-header">
    <nav class="navbar">
      <a href="#" class="brand" aria-label="Smart phone store home">
        <span class="brand-mark" aria-hidden="true">
          <svg viewBox="0 0 64 64" role="img" focusable="false">
            <defs>
              <linearGradient id="phoneGlow" x1="0%" y1="0%" x2="100%" y2="100%">
                <stop offset="0%" stop-color="#17c6b5" />
                <stop offset="100%" stop-color="#0d7ef2" />
              </linearGradient>
            </defs>
            <rect x="18" y="8" width="28" height="48" rx="8" fill="url(#phoneGlow)" />
            <rect x="22" y="13" width="20" height="34" rx="4" fill="#09111f" />
            <circle cx="32" cy="51" r="2.8" fill="#e8f4ff" />
            <path
              d="M42 17c4.2 1.5 7 5.4 7 10s-2.8 8.5-7 10"
              fill="none"
              stroke="#9fe8ff"
              stroke-linecap="round"
              stroke-width="3"
            />
            <path
              d="M46.5 12c6.1 2.1 10.5 8 10.5 15s-4.4 12.9-10.5 15"
              fill="none"
              stroke="#9fe8ff"
              stroke-linecap="round"
              stroke-opacity="0.72"
              stroke-width="3"
            />
          </svg>
        </span>

        <span class="brand-copy">
          <strong>NovaMobile</strong>
          <small>Smartphone Store</small>
        </span>
      </a>

      <button
        class="menu-toggle"
        type="button"
        :aria-expanded="isMenuOpen"
        aria-label="Toggle navigation menu"
        @click="isMenuOpen = !isMenuOpen"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <div class="nav-links" :class="{ open: isMenuOpen }">
        <a href="#phones" @click="closeMenu">Phones</a>
        <a href="#brands" @click="closeMenu">Brands</a>
        <a href="#deals" @click="closeMenu">Deals</a>
        <a href="#accessories" @click="closeMenu">Accessories</a>
        <a href="#support" @click="closeMenu">Support</a>
      </div>

      <div class="nav-actions" :class="{ open: isMenuOpen }">
        <a href="#search" class="icon-btn" aria-label="Search">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <circle cx="11" cy="11" r="7"></circle>
            <path d="m20 20-3.5-3.5"></path>
          </svg>
        </a>
        <a href="#cart" class="icon-btn" aria-label="Shopping cart">
          <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M3 4h2l2.1 10.2a2 2 0 0 0 2 1.6H17a2 2 0 0 0 2-1.5L21 7H8"></path>
            <circle cx="10" cy="19" r="1.5"></circle>
            <circle cx="18" cy="19" r="1.5"></circle>
          </svg>
        </a>
        <a href="#shop-now" class="cta" @click="closeMenu">Shop Now</a>
      </div>
    </nav>
  </header>
</template>


<style scoped>
:global(*) {
  box-sizing: border-box;
}

.store-header {
  --nav-bg: rgba(6, 13, 24, 0.9);
  --nav-border: rgba(159, 232, 255, 0.16);
  --text-main: #f6fbff;
  --text-soft: #9fb6c9;
  --accent-a: #17c6b5;
  --accent-b: #0d7ef2;
  --surface: rgba(255, 255, 255, 0.06);
  --surface-strong: rgba(255, 255, 255, 0.12);
  padding: 18px 24px;
  background:
    radial-gradient(circle at top left, rgba(23, 198, 181, 0.22), transparent 28%),
    radial-gradient(circle at top right, rgba(13, 126, 242, 0.2), transparent 24%),
    linear-gradient(135deg, #02060d, #08111f 48%, #07182c);
  color: var(--text-main);
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

.navbar {
  width: min(1200px, 100%);
  margin: 0 auto;
  display: grid;
  grid-template-columns: auto 1fr auto;
  align-items: center;
  gap: 24px;
  padding: 16px 22px;
  border: 1px solid var(--nav-border);
  border-radius: 24px;
  background: var(--nav-bg);
  backdrop-filter: blur(18px);
  box-shadow: 0 18px 45px rgba(0, 0, 0, 0.22);
}

.brand {
  display: inline-flex;
  align-items: center;
  gap: 14px;
  color: var(--text-main);
  text-decoration: none;
}

.brand-mark {
  width: 56px;
  height: 56px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 18px;
  background: linear-gradient(145deg, rgba(255, 255, 255, 0.12), rgba(255, 255, 255, 0.04));
  box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08);
}

.brand-mark svg {
  width: 40px;
  height: 40px;
}

.brand-copy {
  display: flex;
  flex-direction: column;
  line-height: 1.1;
}

.brand-copy strong {
  font-size: 1.1rem;
  letter-spacing: 0.02em;
}

.brand-copy small {
  margin-top: 4px;
  color: var(--text-soft);
  font-size: 0.78rem;
  text-transform: uppercase;
  letter-spacing: 0.18em;
}

.nav-links,
.nav-actions {
  display: flex;
  align-items: center;
  gap: 10px;
}

.nav-links {
  justify-content: center;
  flex-wrap: wrap;
}

.nav-links a {
  color: var(--text-soft);
  text-decoration: none;
  font-size: 0.96rem;
  padding: 10px 14px;
  border-radius: 999px;
  transition: background-color 0.2s ease, color 0.2s ease, transform 0.2s ease;
}

.nav-links a:hover {
  color: var(--text-main);
  background: var(--surface);
  transform: translateY(-1px);
}

.nav-actions {
  justify-content: flex-end;
}

.icon-btn,
.cta {
  text-decoration: none;
}

.icon-btn {
  width: 44px;
  height: 44px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  color: var(--text-main);
  background: var(--surface);
  transition: background-color 0.2s ease, transform 0.2s ease;
}

.icon-btn:hover {
  background: var(--surface-strong);
  transform: translateY(-1px);
}

.icon-btn svg {
  width: 20px;
  height: 20px;
}

.cta {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 44px;
  padding: 0 18px;
  border-radius: 999px;
  color: #f6fbff;
  font-weight: 700;
  background: linear-gradient(135deg, var(--accent-a), var(--accent-b));
  box-shadow: 0 10px 24px rgba(13, 126, 242, 0.28);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.cta:hover {
  transform: translateY(-1px);
  box-shadow: 0 14px 30px rgba(13, 126, 242, 0.36);
}

.menu-toggle {
  display: none;
  width: 46px;
  height: 46px;
  border: 0;
  border-radius: 14px;
  background: var(--surface);
  cursor: pointer;
}

.menu-toggle span {
  display: block;
  width: 20px;
  height: 2px;
  margin: 4px auto;
  background: var(--text-main);
  border-radius: 999px;
}

@media (max-width: 920px) {
  .navbar {
    grid-template-columns: auto auto;
    justify-content: space-between;
  }

  .menu-toggle {
    display: inline-block;
  }

  .nav-links,
  .nav-actions {
    display: none;
    grid-column: 1 / -1;
    width: 100%;
    flex-direction: column;
    align-items: stretch;
  }

  .nav-links.open,
  .nav-actions.open {
    display: flex;
  }

  .nav-links {
    margin-top: 4px;
    padding-top: 12px;
    border-top: 1px solid var(--nav-border);
  }

  .nav-links a,
  .cta,
  .icon-btn {
    justify-content: center;
  }

  .nav-actions {
    padding-top: 6px;
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
  }
}

@media (max-width: 640px) {
  .store-header {
    padding: 12px;
  }

  .navbar {
    padding: 14px;
    gap: 16px;
  }

  .brand {
    gap: 10px;
  }

  .brand-mark {
    width: 48px;
    height: 48px;
  }

  .brand-copy strong {
    font-size: 1rem;
  }

  .brand-copy small {
    font-size: 0.72rem;
    letter-spacing: 0.14em;
  }
}
</style>