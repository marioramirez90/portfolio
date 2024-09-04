<template>
  <footer class="portfolio-footer">
    <div class="footer-content">
      <div class="social-media">
        <a href="https://github.com/" target="_blank" class="social-link">
          <i class="fab fa-github"></i>
        </a>
        <a href="https://linkedin.com/" target="_blank" class="social-link">
          <i class="fab fa-linkedin"></i>
        </a>
        <a href="https://twitter.com/" target="_blank" class="social-link">
          <i class="fab fa-twitter"></i>
        </a>
      </div>
    </div>
    <div class="footer-bottom">
      <p>&copy; 2024 Mario Ramirez</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'PortfolioFooter'
}
</script>

<style scoped>
.portfolio-footer {
  background-color: var(--background-color);
  color: white;
  padding: 3rem 0;
  text-align: center;
  position: relative;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.5);
  margin-top: 15rem;
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 1.5rem;
  animation: fadeIn 2s ease-in-out;
}

.social-media {
  display: flex;
  gap: 1.5rem;
  margin-bottom: 1rem;
}

.social-link {
  color: var(--line-color);
  font-size: 2rem;
  transition:
    transform 0.3s ease,
    color 0.3s ease,
    box-shadow 0.3s ease;
  position: relative;
}

.social-link::before {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  background: var(--line-color);
  border-radius: 50%;
  transition:
    width 0.3s ease,
    height 0.3s ease;
  transform: translate(-50%, -50%);
  z-index: -1;
}

.social-link:hover::before {
  width: 150%;
  height: 150%;
}

.social-link:hover {
  color: white;
  transform: scale(1.1);
  box-shadow: 0 0 15px var(--line-color);
}

.contact-info p {
  margin: 0.5rem 0;
  font-size: 1.2rem;
  animation: slideUp 1.5s ease-out;
}

.contact-info a {
  color: var(--line-color);
  text-decoration: none;
}

.contact-info a:hover {
  text-decoration: underline;
}

.footer-bottom {
  border-top: 2px solid var(--line-color);
  padding-top: 1rem;
  font-size: 0.9rem;
  animation: shimmer 5s infinite linear;
  background: linear-gradient(
    90deg,
    var(--background-color),
    var(--line-color),
    var(--background-color)
  );
  background-size: 200% auto;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes slideUp {
  0% {
    transform: translateY(20px);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes shimmer {
  0% {
    background-position: -100%;
  }
  100% {
    background-position: 100%;
  }
}
</style>
