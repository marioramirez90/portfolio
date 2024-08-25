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
        <li><a href="#about-me">About me</a></li>
        <li><a href="#projects">Projects</a></li>
        <button class="contact">Contact</button>
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
  margin: o;
  position: absolute;
  padding: 0.5rem;
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
  justify-content: space-around;
  align-items: center;
  margin-top: 0.8rem;
}

.myname {
  font-size: 2rem;
  font-weight: bold;
  color: var(--font-color);

  text-decoration: none;
  margin-left: 4rem;
  transition:
    transform 0.9s ease-in-out,
    font-size 0.9s ease-in-out;
}

.myname:hover {
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
  transition: width 0.9s ease-in-out;
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

.contact {
  background-color: var(--line-color);
  padding: 0.5rem 1.5rem;
  border-radius: 3rem;
  margin-top: -0.3rem;
  border: none;
  box-shadow: 3px 3px 9px black;
  font-weight: 600;
}
.contact:hover {
  background-color: aqua;
}

.navbar-toggle {
  width: 60px;
  height: 45px;
  position: relative;
  margin: 0 auto;
}
.navbar-toggle span {
  width: 100%;
  height: 9px;
  border-radius: 10px;
  background: var(--line-color);
  position: absolute;
  transform: rotate(0deg);
  transition: 0.25sec ease-in-out;
}
span:nth-child(1) {
  top: 0px;
}
span:nth-child(2),
span:nth-child(3) {
  top: 10px;
}
span:nth-child(4) {
  top: 36px;
}
.navbar-toggle.open span:nth-child(1),
.navbar-toggle.open {
  opacity: 0;
  width: 0;
}
.navbar-toggle.open span:nth-child(2) {
  transform: rotate(45deg);
}
.navbar-toggle.open span:nth-child(3) {
  transform: rotate(-45deg);
}
</style>
