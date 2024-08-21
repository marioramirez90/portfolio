<template>
  <nav class="navbar">
    <div class="navbar-container">
      <div class="navbar-name">
        <a class="name" href="#">Mario Ramirez</a>
      </div>
      <ul :class="['navbar-links', { active: isMenuOpen }]">
        <li>
          <div class="github">
            <a href="https://github.com/marioramirez90">
              <img class="logo" src="/src/assets/img/pngegg.png" alt="logo" /><a href="#"
                >Github</a
              ></a
            >
          </div>
        </li>
        <li><a href="#about-me">About me</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
      <div class="navbar-toggle" @click="toggleMenu">
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
  padding: 0.7rem 5rem;
  position: relative;
  background-color: var(--background-color);
  box-shadow: 2px 2px 3px black;
}
.github {
  display: flex;
  gap: 0.5rem;
}

.github:hover {
  scale: 1.1;
  gap: 1rem;
}

.logo {
  width: 20px;
}

.navbar-container {
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
}

.name {
  font-size: 2rem;
  font-weight: bold;
  color: var(--font-color);
  text-decoration: none;
  margin-left: 4rem;
  transition:
    transform 0.3s ease-in-out,
    font-size 0.3s ease-in-out; /* Transition hinzugefügt */
}

.name:hover {
  scale: 1.2;
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
}

.navbar-links a:hover {
  scale: 1.2;
}

.navbar-links li::after {
  content: '';
  position: absolute;
  width: 0%;
  border-radius: 2rem;
  font-size: 2rem;
  height: 0.3rem;
  background-color: var(--line-color);
  left: 0;
  bottom: -8px;
  transition: width 0.3s ease-in-out;
}

.navbar-links li:hover::after {
  width: 100%;
}

.navbar-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
}

.navbar-toggle span {
  width: 25px;
  height: 3px;
  background-color: #fff;
  margin: 4px;
  transition: 0.4s;
}
@media (max-width: 1024px) {
  .navbar {
    padding: 0.7rem 2rem;
  }

  .navbar-container {
    padding: 0.5rem 1rem;
  }

  .navbar-name a {
    font-size: 1.8rem;
    margin-left: 2rem;
  }

  .navbar-links {
    gap: 2rem;
  }

  .logo {
    width: 18px;
  }
}

@media (max-width: 900px) {
  .navbar {
    padding: 0.7rem 1.5rem;
  }

  .navbar-container {
    padding: 0.5rem 0.5rem;
  }

  .navbar-name a {
    font-size: 1.5rem;
    margin-left: 1rem;
  }

  .navbar-links {
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    background-color: #333;
    flex-direction: column;
    align-items: center;
    display: none;
    gap: 1.5rem;
    padding: 1rem;
  }

  .navbar-links a {
    padding: 1rem;
    font-size: 1.2rem;
  }

  .navbar-toggle {
    display: flex;
  }

  .navbar-links.active {
    display: flex;
  }

  .logo {
    width: 16px;
    gap: -4px;
  }
}

@media (max-width: 480px) {
  .navbar {
    padding: 0.7rem 1rem;
  }

  .navbar-container {
    padding: 0.5rem;
  }

  .navbar-name a {
    font-size: 1.3rem;
    margin-left: 0.5rem;
  }

  .navbar-links {
    gap: 1rem;
    padding: 0.5rem;
  }

  .navbar-links a {
    padding: 0.8rem;
    font-size: 1rem;
  }

  .logo {
    width: 14px;
  }
}
</style>
