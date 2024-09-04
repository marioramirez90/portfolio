<template>
  <div class="contact-section">
    <div class="contact-header">
      <h1>Kontaktieren Sie mich</h1>
    </div>
    <form @submit.prevent="sendEmail" class="contact-form">
      <div class="input-group">
        <label for="name">Name</label>
        <input type="text" id="name" v-model="form.name" required placeholder="Ihr Name" />
      </div>
      <div class="input-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="form.email" required placeholder="Ihre Email" />
      </div>
      <div class="input-group">
        <label for="message">Nachricht</label>
        <textarea
          id="message"
          v-model="form.message"
          required
          placeholder="Ihre Nachricht"
        ></textarea>
      </div>
      <button type="submit" class="submit-button" :disabled="isSending">
        <span v-if="!isSending">Senden</span>
        <span v-else class="loader"></span>
      </button>
    </form>
    <div class="contact-info">
      <p>Email: <a href="mailto:mario-ramirez@hotmail.de">mario-ramirez@hotmail.de</a></p>
      <p>Telefon: <a href="tel:+4915221367971">01522 1367971</a></p>
      <p>Adresse: Hamburg, 22417</p>
    </div>
  </div>
</template>

<script>
import emailjs from 'emailjs-com'

export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      },
      isSending: false // Zustand für die Senden-Animation
    }
  },
  methods: {
    sendEmail() {
      this.isSending = true // Start der Senden-Animation
      emailjs
        .send(
          'service_phuf10b', // Dein EmailJS Service ID
          'template_e5yb4dh', // Deine EmailJS Template ID
          {
            name: this.form.name,
            email: this.form.email,
            message: this.form.message
          },
          'your_user_id' // Deine EmailJS User ID
        )
        .then(
          () => {
            alert('Nachricht wurde erfolgreich gesendet!')
            this.resetForm()
          },
          (error) => {
            alert('Fehler beim Senden der Nachricht. Bitte versuchen Sie es erneut.')
            console.error(error)
          }
        )
        .finally(() => {
          this.isSending = false // Ende der Senden-Animation
        })
    },
    resetForm() {
      this.form.name = ''
      this.form.email = ''
      this.form.message = ''
    }
  }
}
</script>

<style scoped>
.contact-section {
  margin-top: 15rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 4rem;
  color: var(--line-color);
  border-radius: 0 0 20rem 20rem;
  position: relative;
  overflow: hidden;
}

.contact-header {
  margin-bottom: 2rem;
}

.contact-header h1 {
  font-size: 4rem;
  color: var(--line-color);
  font-weight: 900;
  margin-bottom: 1rem;
  text-align: center;
  background-image: linear-gradient(90deg, var(--line-color), #00a080);
  background-size: 200% auto;
  color: transparent;
  -webkit-background-clip: text;
  background-clip: text;
  animation: shine 3s linear infinite;
}

@keyframes shine {
  to {
    background-position: 200% center;
  }
}

.contact-form {
  width: 100%;
  max-width: 600px;
  padding: 2rem;
  border-radius: 1rem;
  background-color: var(--background-color);
  box-shadow: 0 0 15px rgba(6, 6, 6, 0.5);
}

.input-group {
  margin-bottom: 1.5rem;
  position: relative;
}

.input-group label {
  display: block;
  margin-bottom: 0.5rem;
  color: var(--line-color);
  font-size: 1.2rem;
}

.input-group input,
.input-group textarea {
  width: 100%;
  padding: 0.75rem;
  border: 2px solid var(--line-color);
  background-color: transparent;
  color: white;
  border-radius: 5px;
  outline: none;
  font-size: 1rem;
  transition:
    border-color 0.3s ease,
    box-shadow 0.3s ease;
}

.input-group input:focus,
.input-group textarea:focus {
  border-color: #00a080;
  box-shadow: 0 0 10px rgba(0, 255, 200, 0.8);
}

.submit-button {
  width: 100%;
  background-color: transparent; /* Transparenter Hintergrund */
  color: var(--line-color);
  border: 2px solid var(--line-color);
  padding: 0.75rem 1.5rem;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition:
    transform 0.3s ease,
    background-color 0.3s ease,
    color 0.3s ease;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}

.submit-button:hover {
  transform: scale(1.05);
  background-color: rgba(0, 255, 204, 0.2);
}

.loader {
  border: 3px solid transparent;
  border-top: 3px solid var(--line-color);
  border-radius: 50%;
  width: 20px;
  height: 20px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}

.contact-info {
  margin-top: 2rem;
  text-align: center;
  color: var(--line-color);
  font-size: 1.2rem;
}

.contact-info a {
  color: var(--line-color);
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-info a:hover {
  color: #00a080;
}
</style>
