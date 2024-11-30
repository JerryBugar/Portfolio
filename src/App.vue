<template>
  <div class="main-wrapper">
    <div class="background-overlay"></div>
    <div class="container-fluid p-0">
      <Navbar />
      <main class="container mt-5 pt-5">
        <About />
        <Projects />
        <Skills />
        <SocialMedia />
      </main>
      <Footer/>
    </div>
  </div>
</template>

<script setup>
import Navbar from './components/Navbar.vue';
import About from './components/About.vue';
import Projects from './components/Projects.vue';
import Skills from './components/Skills.vue';
import SocialMedia from './components/SocialMedia.vue';
import Footer from './components/Footer.vue';
</script>

<style>
.main-wrapper {
  min-height: 100vh;
  position: relative;
  background: linear-gradient(45deg, #2c3e50, #c0392b, #e74c3c);
  background-size: 400% 400%;
  animation: gradientBG 15s ease infinite;
}

.background-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: 
    radial-gradient(circle at 20% 20%, rgba(44, 62, 80, 0.15) 0%, transparent 40%),
    radial-gradient(circle at 80% 80%, rgba(231, 76, 60, 0.1) 0%, transparent 40%);
  pointer-events: none;
  z-index: 1;
}

/* Container utama */
.container-fluid {
  position: relative;
  z-index: 2;
}

/* Style untuk section */
section {
  background: rgba(34, 34, 34, 0.9);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 2rem;
  margin-bottom: 2rem;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
  border: 1px solid rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease;
}

section:hover {
  transform: translateY(-5px);
}

@keyframes gradientBG {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

/* Responsif untuk mobile */
@media (max-width: 768px) {
  section {
    margin: 1rem;
    padding: 1rem;
  }
}
</style>