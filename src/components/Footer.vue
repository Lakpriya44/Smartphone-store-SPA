<script setup lang="ts">

</script>

<template>
  <footer class="store-footer">
    <div class="footer-shell">
      <section class="brand-panel">
        <a href="#" class="brand" aria-label="NovaMobile home">
          <span class="brand-mark" aria-hidden="true">
            <svg viewBox="0 0 64 64" role="img" focusable="false">
              <defs>
                <linearGradient id="footerPhoneGlow" x1="0%" y1="0%" x2="100%" y2="100%">
                  <stop offset="0%" stop-color="#17c6b5" />
                  <stop offset="100%" stop-color="#0d7ef2" />
                </linearGradient>
              </defs>
              <rect x="18" y="8" width="28" height="48" rx="8" fill="url(#footerPhoneGlow)" />
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

        <p class="brand-text">
          Premium smartphones, trusted brands, and fast islandwide delivery for customers who
          want their next device without the hassle.
        </p>

        <div class="contact-list">
          <a href="tel:+94112345678">+94 11 234 5678</a>
          <a href="mailto:support@novamobile.com">support@novamobile.com</a>
          <span>45 Market Street, Colombo</span>
        </div>
      </section>

      <section class="link-panel">
        <h3>Shop</h3>
        <a href="#new-arrivals">New Arrivals</a>
        <a href="#best-sellers">Best Sellers</a>
        <a href="#trade-in">Trade-In</a>
        <a href="#accessories">Accessories</a>
      </section>

      <section class="link-panel">
        <h3>Support</h3>
        <a href="#order-tracking">Order Tracking</a>
        <a href="#warranty">Warranty</a>
        <a href="#faq">FAQ</a>
        <a href="#contact">Contact Us</a>
      </section>

      <section class="newsletter-panel">
        <h3>Stay Updated</h3>
        <p>
          Get launch alerts, flash deals, and expert phone picks straight to your inbox.
        </p>

        <form class="newsletter-form" @submit.prevent>
          <label class="sr-only" for="footer-email">Email address</label>
          <input id="footer-email" type="email" placeholder="Enter your email" />
          <button type="submit">Subscribe</button>
        </form>

        <div class="socials" aria-label="Social media links">
          <a href="#instagram" aria-label="Instagram">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <rect x="3" y="3" width="18" height="18" rx="5"></rect>
              <circle cx="12" cy="12" r="4"></circle>
              <circle cx="17.5" cy="6.5" r="1"></circle>
            </svg>
          </a>
          <a href="#facebook" aria-label="Facebook">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path d="M15 3h-3a4 4 0 0 0-4 4v3H5v4h3v7h4v-7h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>
            </svg>
          </a>
          <a href="#youtube" aria-label="YouTube">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
              <path
                d="M22 12s0-3.2-.4-4.7a2.6 2.6 0 0 0-1.8-1.8C18.3 5 12 5 12 5s-6.3 0-7.8.5A2.6 2.6 0 0 0 2.4 7.3C2 8.8 2 12 2 12s0 3.2.4 4.7a2.6 2.6 0 0 0 1.8 1.8C5.7 19 12 19 12 19s6.3 0 7.8-.5a2.6 2.6 0 0 0 1.8-1.8c.4-1.5.4-4.7.4-4.7Z"
              ></path>
              <path d="m10 9 5 3-5 3V9Z"></path>
            </svg>
          </a>
        </div>
      </section>
    </div>

    <div class="footer-bottom">
      <span>&copy; 2026 NovaMobile. All rights reserved.</span>
      <div class="legal-links">
        <a href="#privacy">Privacy Policy</a>
        <a href="#terms">Terms of Service</a>
      </div>
    </div>
  </footer>
</template>

<script setup>
</script>

<style scoped>
:global(*) {
  box-sizing: border-box;
}

.store-footer {
  --footer-bg: #05101c;
  --footer-panel: rgba(255, 255, 255, 0.05);
  --footer-border: rgba(159, 232, 255, 0.12);
  --text-main: #f6fbff;
  --text-soft: #9fb6c9;
  --accent-a: #17c6b5;
  --accent-b: #0d7ef2;
  padding: 28px 24px 20px;
  background:
    radial-gradient(circle at left top, rgba(23, 198, 181, 0.16), transparent 28%),
    radial-gradient(circle at right bottom, rgba(13, 126, 242, 0.18), transparent 24%),
    linear-gradient(180deg, #06111f, var(--footer-bg));
  color: var(--text-main);
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}

.footer-shell {
  width: min(1200px, 100%);
  margin: 0 auto;
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr 1.3fr;
  gap: 24px;
  padding: 28px;
  border: 1px solid var(--footer-border);
  border-radius: 28px;
  background: rgba(6, 13, 24, 0.84);
  backdrop-filter: blur(18px);
  box-shadow: 0 20px 48px rgba(0, 0, 0, 0.2);
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

.brand-panel,
.link-panel,
.newsletter-panel {
  min-width: 0;
}

.brand-text,
.newsletter-panel p {
  margin: 18px 0 0;
  color: var(--text-soft);
  line-height: 1.7;
}

.contact-list {
  display: grid;
  gap: 10px;
  margin-top: 18px;
}

.contact-list a,
.contact-list span,
.link-panel a,
.legal-links a {
  color: var(--text-soft);
  text-decoration: none;
  transition: color 0.2s ease;
}

.contact-list a:hover,
.link-panel a:hover,
.legal-links a:hover,
.socials a:hover {
  color: var(--text-main);
}

.link-panel h3,
.newsletter-panel h3 {
  margin: 0 0 14px;
  font-size: 1rem;
}

.link-panel {
  display: grid;
  align-content: start;
  gap: 12px;
}

.newsletter-form {
  display: grid;
  grid-template-columns: 1fr auto;
  gap: 10px;
  margin-top: 18px;
}

.newsletter-form input {
  min-width: 0;
  padding: 14px 16px;
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 14px;
  background: var(--footer-panel);
  color: var(--text-main);
  outline: none;
}

.newsletter-form input::placeholder {
  color: #84a0b5;
}

.newsletter-form button {
  padding: 14px 18px;
  border: 0;
  border-radius: 14px;
  color: #f6fbff;
  font-weight: 700;
  background: linear-gradient(135deg, var(--accent-a), var(--accent-b));
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  box-shadow: 0 10px 24px rgba(13, 126, 242, 0.24);
}

.newsletter-form button:hover {
  transform: translateY(-1px);
  box-shadow: 0 14px 28px rgba(13, 126, 242, 0.34);
}

.socials {
  display: flex;
  gap: 12px;
  margin-top: 20px;
}

.socials a {
  width: 42px;
  height: 42px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  color: var(--text-soft);
  background: var(--footer-panel);
  transition: color 0.2s ease, background-color 0.2s ease, transform 0.2s ease;
}

.socials a:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: translateY(-1px);
}

.socials svg {
  width: 18px;
  height: 18px;
}

.footer-bottom {
  width: min(1200px, 100%);
  margin: 18px auto 0;
  padding: 0 8px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 12px;
  color: var(--text-soft);
  font-size: 0.92rem;
}

.legal-links {
  display: flex;
  gap: 18px;
}

.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

@media (max-width: 980px) {
  .footer-shell {
    grid-template-columns: 1fr 1fr;
  }
}

@media (max-width: 700px) {
  .store-footer {
    padding: 16px 12px 18px;
  }

  .footer-shell {
    grid-template-columns: 1fr;
    padding: 22px 18px;
    gap: 22px;
  }

  .newsletter-form {
    grid-template-columns: 1fr;
  }

  .footer-bottom {
    flex-direction: column;
    align-items: flex-start;
    padding: 0 4px;
  }

  .legal-links {
    flex-wrap: wrap;
    gap: 12px;
  }
}
</style>