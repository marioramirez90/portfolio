<template>
  <section class="projects">
    <div class="project-name">
      <h1>Meine Projekte</h1>
    </div>
    <div class="projects-container">
      <div class="project-3d">
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
            <p class="project-text">built with HTML, CSS, JAVASCRIPT</p>
            <div class="project-info">
              Das "Futurama Raketen Spiel" ist ein 2D-Arcade-Spiel, bei dem man eine Rakete steuert
              und UFOs abschießt, um Punkte zu sammeln.
            </div>
            <div class="projects-button">
              <button @click="openInNewTab('https://github.com/marioramirez90/Futurama-game')">Github</button>
              <button @click="openInNewTab('https://futuramagame.netlify.app/')">Live Test</button>
            </div>
          </div>
        </div>
      </div>

      <div class="project-3d">
        <div class="project-1">
          <div class="project-img">
            <img
              class="projects-img-futurama"
              src="/src/assets/img/Design ohne Titel (2).png"
              alt=""
            />
          </div>
          <div class="project-content">
            <h4 class="project-content-heading">To-Do-APP</h4>
            <p class="project-text">built with HTML, CSS, JAVASCRIPT</p>
            <div class="project-info">
              diese ToDo-App kann Aufgaben hinzufügen, als erledigt markieren und nach
              offenen,erledigten Aufgaben filtern und löschen.
            </div>
            <div class="projects-button">
              <button @click="openInNewTab('https://github.com/marioramirez90/To-do-App')">
                Github
              </button>
              <button @click="openInNewTab('https://marioramirez90.github.io/To-do-App/')">
                Live Test
              </button>
            </div>
          </div>
        </div>
      </div>

      <div class="project-3d">
        <div class="project-1">
          <div class="project-img">
            <img class="projects-img-futurama" src="/src/assets/img/Design ohne Titel.png" alt="" />
          </div>
          <div class="project-content">
            <h4 class="project-content-heading">TheardHub</h4>
            <p class="project-text">built with Vue.js</p>
            <div class="project-info">
              ThreadHub ist eine Frage-Antwort-App, die es Nutzern ermöglicht, Fragen zu stellen und
              Antworten von der Community zu erhalten.
            </div>
            <div class="projects-button">
              <button
                @click="
                  openInNewTab(
                    'https://github.com/coding-bootcamps-eu/final-project-2024-05-threadhub'
                  )
                "
              >
                github
              </button>
              <button @click="openInNewTab('https://threadhub.netlify.app/login')">
                Live Test
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  methods: {
    openInNewTab(url) {
      window.open(url, '_blank')
    }
  },
  mounted() {
    const projects = document.querySelectorAll('.project-1')

    projects.forEach((project) => {
      project.addEventListener('mousemove', (e) => {
        const rect = project.getBoundingClientRect()
        const x = (e.clientX - rect.left) / rect.width
        const y = (e.clientY - rect.top) / rect.height

        project.style.setProperty('--mouse-x', x)
        project.style.setProperty('--mouse-y', y)
      })

      project.addEventListener('mouseleave', () => {
        project.style.setProperty('--mouse-x', 0.5)
        project.style.setProperty('--mouse-y', 0.5)
      })
    })
  }
}
</script>

<style scoped>
.projects {
  background-color: var(--background-color);
  padding-bottom: 15rem;
  box-shadow: 1px 5px 8rem black;
  border-top: 7px solid var(--line-color);
}

.project-name {
  text-align: end;
  margin-top: 7rem;
  font-size: 3rem;
  color: var(--line-color);
  font-weight: 900;
  @supports (background-clip: text) or (-webkit-background-clip: text) {
    background-image: url("data:image/svg+xml,%3Csvg width='2250' height='900' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg%3E%3Cpath fill='%2300A080' d='M0 0h2255v899H0z'/%3E%3Ccircle cx='366' cy='207' r='366' fill='%2300FDCF'/%3E%3Ccircle cx='1777.5' cy='318.5' r='477.5' fill='%2300FDCF'/%3E%3Ccircle cx='1215' cy='737' r='366' fill='%23008060'/%3E%3C/g%3E%3C/svg%3E%0A");
    background-size: 30% auto;
    background-position: center;
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    justify-content: center;
    text-align: center;
  }
}
.projects-container {
  display: flex;
  flex-wrap: wrap;
  padding-top: 4rem;
  padding-bottom: 4rem;
  margin-left: 0.7rem;
  margin-right: 0.7rem;
  padding: 5rem;
  margin: 2rem;
}
.project-3d {
  flex: 1 0 0px;
  perspective: 30rem;
  margin: 1.5rem;
}
.project-1 {
  background-color: white;
  box-shadow: 0.5rem 0.5rem 1rem black;
  border-left: 0.5px solid rgba(128, 128, 128, 0.53);
  border-right: 0.5px solid rgba(128, 128, 128, 0.502);
  border-top: 0.5px solid rgba(128, 128, 128, 0.505);
  border-bottom: 0.75rem solid mediumspringgreen;
  padding-bottom: 3rem;
  transition: transform 0.5s ease;
  transform-style: preserve-3d;
}

.project-1:hover {
  transform: rotateX(calc((var(--mouse-y, 0.5) - 0.5) * -15deg))
    rotateY(calc((var(--mouse-x, 0.5) - 0.5) * 15deg));
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
  max-height: 6rem;
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
  border-radius: 12px;
  padding: 1rem 3rem;
  border: 0.2px solid black;
  background-color: white;
}
.projects-button button:hover {
  border: 1px solid mediumspringgreen;
}
.projects-button :last-child {
  background: linear-gradient(to bottom right, #04ecc9, #5affd3);
  border: 0;
  border-radius: 12px;
  color: #ffffff;
  cursor: pointer;
  display: inline-block;
  font-weight: 500;
  line-height: 2.5;
  outline: transparent;
  padding: 0 2rem;
  text-align: center;
  text-decoration: none;
  transition: box-shadow 0.2s ease-in-out;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  white-space: nowrap;
}
.projects-button button:last-child:not([disabled]):focus {
  box-shadow:
    0 0 0.25rem rgba(0, 0, 0, 0.5),
    -0.125rem -0.125rem 1rem rgba(15, 219, 165, 0.5),
    0.125rem 0.125rem 1rem rgba(5, 184, 220, 0.5);
}

.projects-button button:last-child:not([disabled]):hover {
  box-shadow:
    0 0 0.25rem rgba(0, 0, 0, 0.5),
    -0.125rem -0.125rem 1rem rgba(4, 118, 72, 0.5),
    0.125rem 0.125rem 1rem rgba(6, 241, 190, 0.5);
}

.project-3d {
  perspective: 50rem;
}

@media (max-width: 768px) {
  .project-name {
    font-size: 2rem;
    text-align: center;
    margin-top: 3rem;
  }
  .project-name h1 {
    font-size: 3rem;
  }

  .projects-container {
    padding: 2rem;
    margin: 0;
  }

  .project-3d {
    flex: 1 0 100%;
    margin: 1rem 0;
  }

  .project-1 {
    padding: 2rem;
  }

  .project-content-heading {
    font-size: 1.5rem;
  }

  .project-text,
  .project-info {
    font-size: 0.9rem;
  }

  .projects-button {
    flex-direction: column;
    gap: 1rem;
  }

  .projects-button button {
    padding: 0.75rem 1.5rem;
    font-size: 0.9rem;
  }
}
</style>
