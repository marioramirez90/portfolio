<template>
  <div class="skills-container">
    <div class="my-skills-name">
      <h1>Meine Fähigkeiten</h1>
      <p>
        Ich habe meine Fähigkeiten in der Frontend-Entwicklung geschärft und bin in der Lage,
        erfolgreich eine Vielzahl von praxisnahen Projekten zu erstellen und umzusetzen.
      </p>
    </div>
    <div class="my-skills">
      <div>
        <img
          src="/src/assets/img/icons8-view-js-96.png"
          alt="Vue"
          data-popup="Vue.js hat mir ermöglicht, komplexe Single-Page-Applications zu erstellen. Ich habe gelernt, wie man mit Vue-Komponenten arbeitet, den Zustand der Anwendung mit Vuex verwaltet und Routing mit Vue Router implementiert."
        />
        <p>Vue</p>
      </div>

      <div>
        <img
          src="/src/assets/img/icons8-html-96.png"
          alt="HTML"
          data-popup="Durch das Coding Bootcamp habe ich eine fundierte Basis in HTML5 entwickelt. Ich habe gelernt, wie man Webseiten strukturiert und semantische HTML-Elemente verwendet, um eine klare und zugängliche Website-Struktur zu schaffen."
        />
        <p>HTML</p>
      </div>

      <div>
        <img
          src="/src/assets/img/icons8-css-96.png"
          alt="CSS"
          data-popup="Ich habe meine Fähigkeiten in CSS3 verfeinert, um ansprechende und responsive Designs zu erstellen. Mit Techniken wie Flexbox, Grid und SASS kann ich Webseiten gestalten, die auf verschiedenen Geräten gut aussehen und funktionieren."
        />
        <p>CSS</p>
      </div>

      <div>
        <img
          src="/src/assets/img/icons8-js-96.png"
          alt="JavaScript"
          data-popup="Im Bootcamp habe ich tiefgehende Kenntnisse in JavaScript erworben, von den Grundlagen bis hin zu fortgeschrittenen Konzepten wie asynchroner Programmierung. Ich kann interaktive Webanwendungen entwickeln und moderne JavaScript-Features effektiv einsetzen."
        />
        <p>JavaScript</p>
      </div>

      <div>
        <img
          src="/src/assets/img/icons8-git-96.png"
          alt="Git"
          data-popup="Ich habe Git umfassend genutzt, um den Code zu versionieren und die Zusammenarbeit im Team zu koordinieren. Das Arbeiten mit Branches, Merges und Repositories auf GitHub gehört zu meinen täglichen Aufgaben."
        />
        <p>Git und GitHub</p>
      </div>

      <div>
        <img
          src="/src/assets/img/icons8-nodejs-96.png"
          alt="Node.js"
          data-popup="Mit Node.js habe ich solide Fähigkeiten in der Backend-Entwicklung aufgebaut. Ich kann serverseitige Anwendungen entwickeln und mit Datenbanken integrieren, um leistungsfähige Backend-Lösungen zu erstellen."
        />
        <p>Node und NPM</p>
      </div>

      <div>
        <img
          src="/src/assets/img/icons8-medien-anfragen-96.png"
          alt="Responsive Design"
          data-popup="Ich beherrsche die Prinzipien des Responsive Designs, um sicherzustellen, dass Webseiten auf allen Geräten optimal dargestellt werden. Durch den Einsatz von Media Queries und flexiblen Layouts kann ich benutzerfreundliche Designs erstellen, die sich nahtlos an verschiedene Bildschirmgrößen anpassen."
        />
        <p>responsives Design</p>
      </div>

      <div>
        <img
          src="/src/assets/img/Api.png"
          alt="REST API"
          data-popup="Ich habe Erfahrung darin, externe APIs in Webanwendungen zu integrieren. Dabei habe ich gelernt, wie man API-Daten abruft, verarbeitet und in meine Anwendungen einbindet, um interaktive und datengetriebene Funktionen zu ermöglichen."
        />
        <p>Rest-API</p>
      </div>
    </div>
  </div>

  <!-- Popup Container -->
  <div id="popup" class="popup">
    <div class="popup-content">
      <span class="popup-close">&times;</span>
      <p id="popup-text"></p>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    const popup = document.getElementById('popup')
    const popupText = document.getElementById('popup-text')
    const popupClose = document.querySelector('.popup-close')

    document.querySelectorAll('.my-skills img').forEach((img) => {
      img.addEventListener('click', () => {
        popupText.textContent = img.getAttribute('data-popup')
        popup.style.display = 'block'
      })
    })

    popupClose.addEventListener('click', () => {
      popup.style.display = 'none'
    })

    window.addEventListener('click', (event) => {
      if (event.target === popup) {
        popup.style.display = 'none'
      }
    })
  }
}
</script>

<style scoped>
.skills-container {
  margin: 4rem;
  display: flex;
  flex-direction: row-reverse;
  position: relative;
  gap: 1rem;
  right: 0;
  top: 2.5rem;
  padding-bottom: 15rem;
  padding-top: 5rem;
  margin-bottom: 15;
}
.my-skills {
  text-align: center;
  display: grid;
  grid-template-columns: 1.3fr 1.3fr 1.3fr 1.3fr;
  padding: 5rem;
  gap: 2rem;
  justify-content: center;
}
.my-skills img {
  width: 80px;
  transition: transform 1s ease-in-out;
}
.my-skills img:hover {
  transform: rotate(360deg);
}
.my-skills p {
  margin-top: 1px;
  font-size: 1.2rem;
  color: var(--font-color);
}
.my-skills-name p {
  text-align: end;
  color: var(--font-color);
}
.my-skills-name h1 {
  text-align: end;
  margin-top: 7rem;
  font-size: 4.33rem;
  color: var(--line-color);
  font-weight: 900;
  @supports (background-clip: text) or (-webkit-background-clip: text) {
    background-image: url("data:image/svg+xml,%3Csvg width='2250' height='900' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg%3E%3Cpath fill='%2300A080' d='M0 0h2255v899H0z'/%3E%3Ccircle cx='366' cy='207' r='366' fill='%2300FDCF'/%3E%3Ccircle cx='1777.5' cy='318.5' r='477.5' fill='%2300FDCF'/%3E%3Ccircle cx='1215' cy='737' r='366' fill='%23008060'/%3E%3C/g%3E%3C/svg%3E%0A");
    background-size: 110% auto;
    background-position: center;
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
  }
}

.line {
  display: flex;
  background-color: var(--font-color);
  height: 1rem;
  width: 5rem;
}
.popup {
  display: none;
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.5);
  z-index: 1000;
}

.popup-content {
  display: flex;
  position: absolute;
  flex-direction: column;
  background-color: #000000aa;
  margin: 15% auto;
  padding: 2rem;
  border: 2px solid var(--line-color);
  width: 20%;
  height: 40%;
  margin-left: 17rem;
  margin-top: 28rem;
  color: aqua;
}

.popup-close {
  display: flex;
  margin: 0;
  color: var(--line-color);
  float: right;
  font-size: 28px;
  font-weight: bold;
  justify-content: end;
}

.popup-close:hover,
.popup-close:focus {
  color: black;
  text-decoration: none;
  cursor: pointer;
}
</style>
