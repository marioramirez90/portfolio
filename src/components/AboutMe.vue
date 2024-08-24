<template>
  <div class="about-me">
    <div class="name">
      <h2>Hello! my Name is</h2>
      <h1>Mario Ramirez</h1>
      <p>FRONTEND DEVELOPER</p>
    </div>
  </div>
  <div class="aboutme-content">
    <h1>About Me</h1>
    <p>
      Hello, I am a front-end developer from Germany. I am 34 years old and live with my wife and
      our children in Hamburg. My strengths include commitment, reliability, communication skills,
      and self-reflection.
    </p>

    <p>
      I developed my front-end skills primarily through my training at Coding Bootcamp Europe in
      Berlin, where I had the opportunity to work on numerous projects. You can find a selection of
      these projects in the portfolio section.
    </p>
    <p>
      I especially enjoy working in agile teams, the challenging nature of software development, and
      the wide range of learning opportunities it offers. I am excited to take on more projects!
    </p>
  </div>
</template>
<script>
export default {}
</script>
<style scoped>
.about-me {
  display: flex;
  justify-content: end;
  margin-bottom: 1rem;
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
  border-top: 2px solid rgb(0, 255, 200);
  left: 19rem;
  text-align: left;
  background-color: var(--background-color);
  padding: 5rem;
  box-shadow: 1px 5px 8rem black;
  color: white;
  border-radius: 0 -89rem 0 0;
  text-justify: distribute;
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
    margin-bottom: 1px;
  }
}
.aboutme-content p {
  width: 50%;
  font-size: 1.2rem;
  font-weight: 400;
  margin-bottom: 5px;
}
</style>
