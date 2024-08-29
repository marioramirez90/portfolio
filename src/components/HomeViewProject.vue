<template>
  <section class="projects">
    <div class="projects-container">
      <div class="project-1">
        <div class="project-img">
          <img
            class="projects-img-futurama"
            src="/src/assets/img/Design ohne Titel (1).png"
            alt=""
          />
        </div>
        <div class="project-content">
          <h4 class="project-content-heading">Futurama Project</h4>
          <p class="project-text">built with HTML,CSS,JAVASCRIPT</p>

          <div class="project-info">
            Das "Futurama Raketen Spiel" ist ein 2D-Arcade-Spiel, bei dem man eine Rakete steuert
            und UFOs abschießt, um Punkte zu sammeln.
          </div>
          <div class="projects-button">
            <button>Github</button>
            <button>Live Test</button>
          </div>
        </div>
      </div>

      <div class="project-1">
        <div class="project-img">
          <img
            class="projects-img-futurama"
            src="/src/assets/img/Design ohne Titel (2).png"
            alt=""
          />
        </div>
        <div class="project-content">
          <h4 class="project-content-heading">Futurama Project</h4>
          <p class="project-text">built with HTML,CSS,JAVASCRIPT</p>

          <div class="project-info">
            Das "Futurama Raketen Spiel" ist ein 2D-Arcade-Spiel, bei dem man eine Rakete steuert
            und UFOs abschießt, um Punkte zu sammeln.
          </div>
          <div class="projects-button">
            <button>Github</button>
            <button>Live Test</button>
          </div>
        </div>
      </div>

      <div class="project-1">
        <div class="project-img">
          <img class="projects-img-futurama" src="/src/assets/img/Design ohne Titel.png" alt="" />
        </div>
        <div class="project-content">
          <h4 class="project-content-heading">Futurama Project</h4>
          <p class="project-text">built with HTML,CSS,JAVASCRIPT</p>

          <div class="project-info">
            Das "Futurama Raketen Spiel" ist ein 2D-Arcade-Spiel, bei dem man eine Rakete steuert
            und UFOs abschießt, um Punkte zu sammeln.
          </div>
          <div class="projects-button">
            <button>Github</button>
            <button>Live Test</button>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {}
</script>
<style scoped>
.projects {
  background-color: var(--background-color);
  padding-top: 7rem;
  padding-bottom: 5rem;
  box-shadow: 1px 5px 8rem black;

  border-top: 3px solid var(--line-color);
}
.projects-container {
  display: flex;
  flex-wrap: wrap;
  padding-top: 4rem;
  padding-bottom: 4rem;
  margin-left: 0.66rem;
  margin-right: 0.66rem;
  padding: 5rem;
  margin: 4rem;
}
.project-1 {
  flex: 1 0 0px;
  margin: 0 1.5rem;
  background-color: white;
  box-shadow: 0.5rem 0.5rem 2rem black;
  border-left: 0.5px solid rgba(128, 128, 128, 0.53);
  border-right: 0.5px solid rgba(128, 128, 128, 0.502);
  border-top: 0.5px solid rgba(128, 128, 128, 0.505);
  border-bottom: 0.75rem solid mediumspringgreen;
  position: relative;
  padding-bottom: 3rem;
}

.project-1::after {
  content: '';
  display: block;
  bottom: 0;
  position: absolute;
  left: 0px;
  right: -1px;
  height: 0.75rem;
  background-color: mediumspringgreen;
}
.project-img {
  position: relative;
  background-color: var(--line-color);
  margin: -0.5px;
}

.project-img::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 4rem;
  background-image: linear-gradient(-5.71deg, white 49.9%, transparent 51.1%);
  background-repeat: no-repeat;
  background-position: 50% 100%;
}
.projects-img-futurama {
  width: 100%;
  filter: grayscale(100%);
  mix-blend-mode: multiply;
}

.project-content {
  padding-left: 1rem;
  padding-right: 1rem;
}
.project-content-heading {
  color: rgb(23, 23, 23);
  font-size: 1.7rem;
  font-weight: 600;
  margin-bottom: 0;
}
.project-text {
  color: mediumseagreen;
  font-size: 1rem;
  font-weight: 600;
}
.project-info {
  margin-top: 1rem;
  border-top: 1.5px solid rgba(128, 128, 128, 0.182);
  border-bottom: 1.5px solid rgba(128, 128, 128, 0.182);
  padding-top: 1rem;
  padding-bottom: 1rem;
  display: flex;
}

.projects-button {
  margin-top: 2rem;
  display: flex;
  justify-content: center;
  gap: 4rem;
}
.projects-button button {
  font-size: 1rem;
  font-weight: 700;
  border-radius: 5px;
  padding: 1rem 3rem;
  border: 1px solid med;
}
.projects-button :last-child {
  background-color: mediumspringgreen;
}
</style>
