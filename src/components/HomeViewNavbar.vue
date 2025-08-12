<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-name">
        <a class="myname" href="#">Mario Ramirez</a>
      </div>
      <ul :class="['navbar-links', { active: isMenuOpen }]">
        <li>
          <div class="github">
            <a href="https://github.com/marioramirez90">
              <img class="logo" src="/src/assets/img/pngegg.png" alt="logo" /><a
                href="https://github.com/marioramirez90"
                >Github</a
              ></a
            >
          </div>
        </li>
        <li><a href="/portfolio/src/components/AboutMe.vue">About me</a></li>
        <li><a href="/portfolio/src/components/HomeViewProject.vue">Projects</a></li>

        <li>
          <a href="mailto:mario-ramirez@hotmail.de" class="contact-button">
            <button>
              Kontakt
              <span></span>
            </button>
          </a>
        </li>
      </ul>
      <div :class="['navbar-toggle', { open: isMenuOpen }]" @click="toggleMenu">
        <span class="navbar-icon"></span>
        <span class="navbar-icon"></span>
        <span class="navbar-icon"></span>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isMenuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    }
  }
}
</script>

<style scoped>
.navbar {
  background-color: var(--background-color);
  box-shadow: 1px 5px 8rem black;
  padding-top: 1rem;
  padding-bottom: 0.5rem;
}
.navbar-container {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 1rem;
}

.myname {
  font-size: 2rem;
  font-weight: bold;
  color: var(--font-color);
  text-decoration: none;
  transition:
    transform 0.9s ease-in-out,
    font-size 0.9s ease-in-out;
}

.myname:hover {
  transform: scale(1.2);
  font-size: 2.3rem;
  text-shadow: 1px 1px 2px rgb(7, 7, 7);
}

.navbar-links {
  list-style: none;
  display: flex;
  gap: 4rem;
}

.navbar-links li {
  position: relative;
}

.navbar-links a {
  color: #fff;
  text-decoration: none;
  font-size: 1.5rem;
  font-weight: 600;
  display: flex;
  gap: 1.5rem;
  position: relative;
}

.navbar-links a::after {
  content: '';
  position: absolute;
  width: 0;
  height: 0.3rem;
  background-color: var(--line-color);
  left: 0;
  bottom: -4px;
  border-radius: 2rem;
  transition: width 0.3s ease-in-out;
}

.navbar-links a:hover::after {
  width: 100%;
}

button {
  border: none;
  display: block;
  position: relative;
  padding: 0.5em 2em;
  font-size: 18px;
  background: transparent;
  cursor: pointer;
  user-select: none;
  overflow: hidden;
  color: rgb(14, 235, 176);
  z-index: 1;
  font-family: inherit;
  font-weight: 500;
  top: -0.67rem;
}

button span {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background: transparent;
  z-index: -1;
  border: 4px solid rgb(14, 235, 176);
}

button span::before {
  content: '';
  display: block;
  position: absolute;
  width: 8%;
  height: 500%;
  background: var(--background-color);
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) rotate(-60deg);
  transition: all 0.7s;
}

button:hover span::before {
  transform: translate(-50%, -50%) rotate(-90deg);
  width: 100%;
  background: rgb(14, 235, 176);
}

button:hover {
  color: white;
}

button:active span::before {
  background: #2751cd;
}

.github {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  transition:
    transform 0.3s ease-in-out,
    gap 0.3s ease-in-out;
}

.github:hover {
  transform: scale(1.1);
  gap: 1rem;
}

.logo {
  width: 20px;
}

.navbar-toggle {
  display: none;
  cursor: pointer;
  position: relative;
  width: 30px;
  height: 30px;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.navbar-icon {
  width: 100%;
  height: 3px;
  background-color: var(--line-color);
  border-radius: 5px;
  transition: all 0.5s ease-in-out;
}

.navbar-toggle.open .navbar-icon:nth-child(1) {
  transform: rotate(45deg) translate(10px, 10px);
}

.navbar-toggle.open .navbar-icon:nth-child(2) {
  opacity: 0;
}

.navbar-toggle.open .navbar-icon:nth-child(3) {
  transform: rotate(-45deg) translate(10px, -10px);
}

@media (max-width: 768px) {
  .navbar-toggle {
    display: flex;
  }

  .navbar-links {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background-color: var(--background-color);
    flex-direction: column;
    align-items: center;
    transform: translateY(-100%);
    opacity: 0;
    margin-top: 0.1rem;
    padding-top: 4rem;
    padding-bottom: 3rem;
    box-shadow: 1px 1px 8px rgb(7, 7, 7);
  }

  .navbar-links.active {
    transform: translateY(0);
    opacity: 1;
  }

  .navbar-container {
    justify-content: space-between;
    margin: 0.5rem;
  }
}
</style>
