<template>
  <section id="skills" class="py-5">
    <div class="title-container mb-5">
      <h2 class="section-title text-center py-3 rounded mx-auto px-5">
        <span class="title-icon">
          <i class="bi bi-tools"></i>
        </span>
        Skills
        <div class="title-underline"></div>
      </h2>
    </div>
    <div class="row g-4">
      <div class="col-md-6" v-for="skill in skills" :key="skill.name">
        <div class="skill-card p-4 rounded hover-effect"
             @mouseenter="skill.isHovered = true"
             @mouseleave="skill.isHovered = false">
          <div class="d-flex align-items-center mb-3">
            <div class="icon-wrapper me-3">
              <img :src="skill.icon" class="skill-icon" :alt="skill.name">
            </div>
            <h5 class="card-title mb-0">{{ skill.name }}</h5>
            <span class="percentage-badge ms-auto">{{ skill.percentage }}%</span>
          </div>
          <div class="progress-wrapper">
            <div class="progress" style="height: 12px">
              <div class="progress-bar" 
                   role="progressbar" 
                   :style="{ width: skill.isHovered ? skill.percentage + '%' : '0%', opacity: skill.isHovered ? '1' : '0' }"
                   aria-valuemin="0" 
                   aria-valuemax="100">
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import jsIcon from '../assets/icons/javascript.png'
import vueIcon from '../assets/icons/vue.png'
import htmlIcon from '../assets/icons/html.png'
import cssIcon from '../assets/icons/css.png'
import phpIcon from '../assets/icons/php.png'
import pyIcon from '../assets/icons/python.png'

const skills = ref([
  { 
    name: 'JavaScript', 
    percentage: 80,
    icon: jsIcon,
    isHovered: false
  },
  { 
    name: 'Vue.js', 
    percentage: 70,
    icon: vueIcon,
    isHovered: false
  },
  { 
    name: 'HTML', 
    percentage: 90,
    icon: htmlIcon,
    isHovered: false
  },
  { 
    name: 'CSS', 
    percentage: 85,
    icon: cssIcon,
    isHovered: false
  },
  {
    name: 'PHP',
    percentage: 80,
    icon: phpIcon,
    isHovered: false
  },
  {
    name: 'PYTHON',
    percentage: 75,
    icon: pyIcon,
    isHovered: false
  }
])
</script>

<style scoped>
.skill-card {
  background: #2a2a2a;
  color: white;
  transition: transform 0.3s ease;
  border: 2px solid rgba(255, 255, 255, 0.1);
  position: relative;
  overflow: hidden;
}

.skill-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, transparent, rgba(13, 110, 253, 0.1), transparent);
  transform: translateX(-100%);
  transition: transform 0.6s;
}

.skill-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(13, 110, 253, 0.2);
  border-color: #0d6efd;
}

.skill-card:hover::before {
  transform: translateX(100%);
}

.icon-wrapper {
  width: 45px;
  height: 45px;
  background: rgba(13, 110, 253, 0.1);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
}

.skill-icon {
  width: 30px;
  height: 30px;
  object-fit: contain;
  transition: transform 0.5s ease;
}

.skill-card:hover .icon-wrapper {
  background: rgba(13, 110, 253, 0.2);
  transform: scale(1.1);
}

.skill-card:hover .skill-icon {
  transform: rotate(360deg) scale(1.1);
}

.percentage-badge {
  background: rgba(13, 110, 253, 0.1);
  color: #0d6efd;
  padding: 4px 12px;
  border-radius: 20px;
  font-weight: bold;
  font-size: 0.9rem;
  transition: all 0.3s ease;
}

.skill-card:hover .percentage-badge {
  background: #0d6efd;
  color: white;
  transform: scale(1.05);
}

.progress {
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 10px;
  overflow: hidden;
}

.progress-bar {
  background: linear-gradient(90deg, #0d6efd, #0099ff);
  position: relative;
  transition: all 1.2s cubic-bezier(0.34, 1.56, 0.64, 1);
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(13, 110, 253, 0.5);
  transform-origin: left;
}

/* Tambahkan animasi baru */
@keyframes progressPulse {
  0% {
    box-shadow: 0 0 10px rgba(13, 110, 253, 0.5);
  }
  50% {
    box-shadow: 0 0 20px rgba(13, 110, 253, 0.7);
  }
  100% {
    box-shadow: 0 0 10px rgba(13, 110, 253, 0.5);
  }
}

.skill-card:hover .progress-bar {
  filter: brightness(120%);
  animation: progressPulse 2s infinite;
}

.progress-wrapper {
  position: relative;
  margin-top: 10px;
}

@keyframes slideIn {
  from {
    transform: translateX(-100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

.skill-card {
  animation: slideIn 0.5s ease-out;
}

.title-container {
  position: relative;
  perspective: 1000px;
  text-align: center; /* Tambahan */
  width: 100%; /* Tambahan */
}

.section-title {
  background: #2a2a2a;
  color: white;
  display: inline-flex;
  align-items: center;
  justify-content: center; /* Tambahan */
  gap: 15px;
  position: relative;
  transition: all 0.3s ease;
  border: 2px solid rgba(255, 255, 255, 0.1);
  overflow: hidden;
  cursor: pointer;
  min-width: 200px; /* Tambahan */
  margin: 0 auto; /* Tambahan */
  padding: 15px 40px; /* Menyesuaikan padding */
}

.section-title:hover {
  transform: translateY(-5px);
  border-color: #0d6efd;
  box-shadow: 0 5px 15px rgba(13, 110, 253, 0.3);
}

.title-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background: rgba(13, 110, 253, 0.1);
  width: 40px;
  height: 40px;
  border-radius: 10px;
  transition: all 0.3s ease;
}

.section-title:hover .title-icon {
  background: #0d6efd;
  transform: rotate(360deg);
}

.title-underline {
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, #0d6efd, #0099ff);
  transform: translateX(-50%);
  transition: width 0.3s ease;
}

.section-title:hover .title-underline {
  width: 100%;
}

/* Tambahkan efek glow */
.section-title::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, transparent, rgba(13, 110, 253, 0.1), transparent);
  transform: translateX(-100%);
  transition: transform 0.6s;
}

.section-title:hover::before {
  transform: translateX(100%);
}

/* Animasi untuk icon */
@keyframes iconRotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.section-title:hover .bi-tools {
  animation: iconRotate 1s ease-in-out;
}

/* Efek hover tambahan */
.section-title:hover {
  letter-spacing: 1px;
  background: linear-gradient(145deg, #2a2a2a, #333);
}

/* Efek pulse untuk icon */
@keyframes iconPulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}

.title-icon i {
  font-size: 1.2rem;
  color: #0d6efd;
  transition: all 0.3s ease;
}

.section-title:hover .title-icon i {
  color: white;
  animation: iconPulse 1s infinite;
}

#skills {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
}

.row {
  width: 100%;
  max-width: 1200px; /* Opsional: membatasi lebar maksimum */
  margin: 0 auto;
}
</style>