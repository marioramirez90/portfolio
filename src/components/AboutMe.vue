<template>
  <div class="about-me">
    <div class="name">
      <h2>Hallo! Mein Name ist</h2>
      <h1>Mario Ramirez</h1>
      <p>FRONTEND DEVELOPER</p>

      <img class="img" src="/src/assets/img/pngwing.com.png" alt="img" @click="scrollToContent" />
    </div>
  </div>

  <div class="aboutme-content" ref="aboutMeSection">
    <h1>Über mich</h1>
    <p>
      Hallo, ich bin ein Frontend-Entwickler aus Deutschland. Ich bin 34 Jahre alt und lebe mit
      meiner Frau und unseren Kindern in Hamburg. Zu meinen Stärken zählen Engagement,
      Zuverlässigkeit, Kommunikationsfähigkeit und die Freude an der Teamarbeit.
    </p>

    <p>
      Meine Fähigkeiten in der Frontend-Entwicklung habe ich vor allem durch meine Ausbildung beim
      Coding Bootcamp Europe in Berlin weiterentwickelt, wo ich die Gelegenheit hatte, an
      zahlreichen Projekten mitzuwirken. Eine Auswahl dieser Projekte finden Sie im
      Portfolio-Bereich.
    </p>
    <p>
      Ich fühle mich in agilen Teams besonders wohl, da ich die kreative Zusammenarbeit und die
      Dynamik der Softwareentwicklung schätze. Die ständige Herausforderung und die vielen
      Möglichkeiten, dazuzulernen, motivieren mich, mein Wissen und meine Fähigkeiten kontinuierlich
      zu erweitern. Ich freue mich darauf, an neuen, spannenden Projekten mitzuwirken!
    </p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      scrollOffsets: [625, 750, 740, 1400],
      clickCount: 0
    }
  },
  methods: {
    scrollToContent() {
      if (this.clickCount < this.scrollOffsets.length) {
        const offset = this.scrollOffsets[this.clickCount]
        window.scrollBy({
          top: offset,
          behavior: 'smooth'
        })
        this.clickCount++
      } else {
        console.log('Alle Scroll-Abstände wurden bereits verwendet.')
      }
    }
  }
}
</script>

<style scoped>
.about-me {
  display: flex;
  justify-content: end;
  height: 100vh;
  margin-bottom: 1rem;
  padding-bottom: 5rem;
}
@keyframes float {
  0% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-20px);
  }
  100% {
    transform: translateY(0);
  }
}
.img {
  position: fixed;
  bottom: 3rem;
  left: 50%;
  width: 40px;
  animation: float 3s ease-in-out infinite;
  cursor: pointer;
  z-index: 10;
}

.name {
  display: flex;
  flex-direction: column;
  margin: 9rem;
  padding: 2rem;
  font-size: 3rem;
  color: var(--font-color);
  position: relative;
  margin-top: 17rem;
}
.name h2 {
  font-size: 2rem;
  margin-bottom: 0;
}

.name h1 {
  margin-top: 0;
  margin-bottom: 1px;
}
.name p {
  margin-top: 1px;
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

.aboutme-content {
  display: flex;
  flex-direction: column;
  border-top: 7px solid rgb(0, 255, 195);
  left: 19rem;
  text-align: left;
  background-color: var(--background-color);
  padding: 5rem;
  box-shadow: 1px 5px 8rem black;
  color: white;
  border-radius: 0 -89rem 0 0;
  text-justify: distribute;
  padding-bottom: 15rem;
  padding-top: 7rem;
}

.aboutme-content h1 {
  font-size: 4rem;
  margin-top: 1px;
  font-size: 4.33rem;
  color: var(--line-color);
  font-weight: 900;
  @supports (background-clip: text) or (-webkit-background-clip: text) {
    background-image: url("data:image/svg+xml,%3Csvg width='2250' height='900' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cg%3E%3Cpath fill='%2300A080' d='M0 0h2255v899H0z'/%3E%3Ccircle cx='366' cy='207' r='366' fill='%2300FDCF'/%3E%3Ccircle cx='1777.5' cy='318.5' r='477.5' fill='%2300FDCF'/%3E%3Ccircle cx='1215' cy='737' r='366' fill='%23008060'/%3E%3C/g%3E%3C/svg%3E%0A");
    background-size: 100% auto;
    background-position: center;
    color: transparent;
    -webkit-background-clip: text;
    background-clip: text;
    margin-bottom: 4rem;
  }
}
.aboutme-content p {
  width: 50%;
  font-size: 1.2rem;
  font-weight: 400;
  margin-bottom: 5px;
}
@media (max-width: 768px) {
  .about-me {
    justify-content: center;
  }

  .name {
    margin: 2rem;
    padding: 1rem;
    font-size: 1.5rem;
    margin-top: 5rem;
  }

  .name h2 {
    font-size: 1.5rem;
  }

  .name p {
    font-size: 2.5rem;
  }

  .aboutme-content {
    left: 0;
    padding: 2rem;
    border-radius: 0;
    padding-bottom: 5rem;
    padding-top: 5rem;
    box-shadow: none;
  }

  .aboutme-content p {
    width: 100%;
    font-size: 1rem;
  }
}
</style>
