<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
    <div class="container">
      <a class="navbar-brand d-flex align-items-center" href="#">
        <div class="brand-wrapper">
          <div class="brand-container">
            <img src="../assets/icons/jepri.jpeg" alt="Profile Icon" class="brand-image rounded-circle" />
            <div class="brand-overlay"></div>
            <span class="brand-text">Jefri</span>
          </div>
          <div class="brand-glow"></div>
        </div>
      </a>
      <button class="navbar-toggler custom-toggler" type="button" @click="toggleMenu">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" :class="{ show: isOpen }">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <a class="nav-link d-flex align-items-center nav-link-hover" 
               @click.prevent="scrollToSection('about')" 
               href="#about">
              <span class="nav-text">Tentang</span>
              <img src="../assets/icons/tentang.gif" alt="Info Icon" class="icon ms-2" />
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link d-flex align-items-center nav-link-hover" 
               @click.prevent="scrollToSection('projects')" 
               href="#projects">
              <span class="nav-text">Proyek</span>
              <img src="../assets/icons/proyek.gif" alt="Project Icon" class="icon ms-2" />
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link d-flex align-items-center nav-link-hover" 
               @click.prevent="scrollToSection('skills')" 
               href="#skills">
              <span class="nav-text">Skill</span>
              <img src="../assets/icons/skill.gif" alt="Tools Icon" class="icon ms-2" />
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link d-flex align-items-center nav-link-hover" 
               @click.prevent="scrollToSection('social-media')" 
               href="#social-media">
              <span class="nav-text">Media Sosial</span>
              <img src="../assets/icons/sosmed.gif" alt="Share Icon" class="icon ms-2" />
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
    scrollToSection(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        const offset = 80;
        const elementPosition = element.getBoundingClientRect().top;
        const offsetPosition = elementPosition + window.pageYOffset - offset;

        window.scrollTo({
          top: offsetPosition,
          behavior: 'smooth',
        });

        this.isOpen = false;
      }
    }
  }
};
</script>

<style scoped>
.navbar {
  backdrop-filter: blur(10px);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
}

.brand-wrapper {
  position: relative;
  padding: 5px;
}

.brand-container {
  position: relative;
  display: flex;
  align-items: center;
  padding: 5px 15px;
  border-radius: 30px;
  background: linear-gradient(45deg, #1a1a1a, #2c2c2c);
  overflow: hidden;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.brand-image {
  width: 40px;
  height: 40px;
  margin-right: 10px;
  transition: transform 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
  z-index: 2;
  backface-visibility: hidden;
  transform-style: preserve-3d;
}

.brand-text {
  font-size: 1.2rem;
  font-weight: bold;
  background: linear-gradient(45deg, #fff, #007bff);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  transition: all 0.5s ease;
  z-index: 2;
}

.brand-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, #007bff33, #00ff8833);
  opacity: 0;
  transition: all 0.4s ease;
}

.brand-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(0);
  width: 100%;
  height: 100%;
  background: radial-gradient(circle, #007bff33, transparent 70%);
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
}

@keyframes smoothRotate {
  0% {
    transform: rotate(0deg) scale(1);
  }
  50% {
    transform: rotate(180deg) scale(1.15);
  }
  100% {
    transform: rotate(360deg) scale(1.1);
  }
}

.brand-container:hover .brand-image {
  animation: smoothRotate 0.6s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
  box-shadow: 0 0 20px rgba(0, 123, 255, 0.5);
}

@keyframes subtlePulse {
  0% { transform: translateY(0) scale(1); }
  50% { transform: translateY(-2px) scale(1.03); }
  100% { transform: translateY(0) scale(1); }
}

.brand-container:hover {
  animation: subtlePulse 1s ease-in-out infinite;
  box-shadow: 0 10px 20px rgba(0, 123, 255, 0.2);
}

.nav-link-hover {
  position: relative;
  overflow: hidden;
}

.nav-link-hover::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 2px;
  background: linear-gradient(90deg, #007bff, #00ff88);
  transition: width 0.3s ease;
}

.nav-link-hover:hover::before {
  width: 100%;
}

.nav-link-hover:hover .nav-text {
  transform: translateY(-2px);
  color: #007bff;
}

.nav-text {
  transition: all 0.3s ease;
}

.icon {
  width: 30px;
  height: 30px;
  transition: all 0.3s ease;
  filter: brightness(1);
}

.nav-link-hover:hover .icon {
  transform: scale(1.2) rotate(10deg);
  filter: brightness(1.2);
}

.custom-toggler {
  border: none;
  padding: 0.5rem;
  transition: all 0.3s ease;
}

.custom-toggler:hover {
  background: rgba(255, 255, 255, 0.1);
  transform: scale(1.1);
}

@media (max-width: 991.98px) {
  .navbar-nav {
    text-align: center;
    padding: 1rem 0;
  }
  
  .nav-link-hover {
    margin: 0.5rem 0;
  }
  
  .nav-link {
    justify-content: center;
  }
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: 80px;
}

.scroll-progress {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 3px;
  background: linear-gradient(90deg, #007bff, #00ff88);
  transform-origin: 0;
  transition: transform 0.3s ease;
  z-index: 1100;
}

.nav-link-hover::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, transparent, rgba(255,255,255,0.1), transparent);
  transform: translateX(-100%);
  transition: transform 0.6s;
}

.nav-link-hover:hover::after {
  transform: translateX(100%);
}

.navbar-collapse {
  transition: all 0.3s ease-in-out;
}

.navbar-collapse.show {
  display: block;
}

@keyframes slideDown {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

:root {
  scroll-behavior: smooth;
  scroll-padding-top: 80px;
}

body {
  scroll-behavior: smooth;
}

.smooth-scroll {
  scroll-behavior: smooth;
  transition: all 0.5s ease-in-out;
}

.scroll-container {
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}

.section-title {
    transition: transform 0.3s ease, opacity 0.3s ease;
}
</style>