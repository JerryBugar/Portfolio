<template>
  <section id="projects" class="py-5">
    <div class="title-container mb-4">
      <h2 class="section-title text-center bg-dark text-white py-3 rounded mx-auto px-5">
        <span class="title-icon me-2">
          <i class="bi bi-code-square"></i>
        </span>
        Proyek
        <div class="title-underline"></div>
      </h2>
    </div>
    <div class="row g-4">
      <div class="col-md-6" v-for="project in projects" :key="project.id">
        <div class="project-card">
          <div class="card h-100 bg-dark text-white hover-card">
            <img :src="project.image" class="card-img-top project-image" :alt="project.name">
            <div class="card-body position-relative">
              <div class="card-icon">
                <i class="bi bi-folder-code"></i>
              </div>
              <h5 class="card-title mb-3">{{ project.name }}</h5>
              <p class="card-text bg-light bg-opacity-75 text-dark rounded p-3">
                {{ project.description }}
              </p>
              <div class="project-links">
                <a :href="project.codeUrl" class="btn btn-outline-primary me-2">
                  <i class="bi bi-github me-1"></i> Kode
                </a>
                <a :href="project.demoUrl" class="btn btn-outline-success">
                  <i class="bi bi-play-circle me-1"></i> Demo
                </a>
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
import project1Image from '../assets/images/project1.png'
import project2Image from '../assets/images/project2.png'
import project3Image from '../assets/images/project3.png'
import project4Image from '../assets/images/project4.png'
import project5Image from '../assets/images/project5.png'

const projects = ref([
  {
    id: 1,
    name: 'Mengetik Cepat',
    description: 'Ini adalah project untuk mengetes seberapa cepat kita mengetik, dengan cara kita harus mengetik setiap kata dan menekan tombol space, bisa memilih waktu 30 atau 60 detik dan bisa memilih mode beginner atau pro. Website ini di buat dengan html, css(Boostrap), Javascript',
    image: project1Image,
    codeUrl: 'https://github.com/JerryBugar/MengetikCepat', // tambahkan URL GitHub project
    demoUrl: 'https://jerrybugar.github.io/MengetikCepat/'  // tambahkan URL demo project
  },
  {
    id: 2,
    name: 'Website Static',
    description: 'Project ini adalah project pertama saya dalam membuat web static yang ditugaskan oleh guru produktif saya. Dan project ini dibuat dengan html, css dan untuk javascript nya saya melihat dokumentasi dari youtube dan google. dan beberapa asset gambar, video, dan gif nya saya dapat dari youtube dan google.',
    image: project2Image,
    codeUrl: 'https://github.com/JerryBugar/Project-web1',
    demoUrl: 'https://jerrybugar.github.io/Project-web1/'
  },
  {
    id: 3,
    name: 'Tiktak toe',
    description: 'Ini adalah project untuk menghilangkan stress dan seru-seruan. Di dalam project tiktak toe yang saya buat, kita bisa memilih lawan komputer atau lawan teman kita sendiri, dan bisa memilih 3 mode kesulitan, mulai dari easy, medium, sampai hard. Dan project ini dibuat menggunakan html,css,javascript.',
    image: project3Image,
    codeUrl: 'https://github.com/JerryBugar/Tiktaktoe',
    demoUrl: 'https://jerrybugar.github.io/Tiktaktoe/'
  },
  {
    id: 4,
    name: 'Password generator',
    description: 'Ini adalah Project untuk membuat password random atau acak yang kuat, kita bisa memilih ingin berapa panjang password nya, dan bisa memilih 3 opsi untuk tambahan keaman password nya, yaitu Numbers, Symbol, dan uppercase, selain itu ketika kita memencet generate kita akan diberitahu password nya kuat atau tidak di dalam indikator webnya. Project ini dibuat menggunakan html, css, dan javascript.',
    image: project4Image,
    codeUrl: 'https://github.com/JerryBugar/Passgenerator',
    demoUrl: 'https://jerrybugar.github.io/Passgenerator/'
  },
  {
    id: 5,
    name: 'Data Siswa',
    description: 'Ini adalah project uprak(ulangan praktek) akhir semester dengan menggunakan php,html,css(boostrap),javascript. Dan memiliki database(phpmyadmin) untuk menyimpan data siswa. Di dalam project ini kita bisa melakukan penambahan dataa siswa, mengubah data siswa, menghapus data siswa, dan melihat detail siswa.',
    image: project5Image,
    codeUrl: 'https://github.com/JerryBugar/Uprakphp',
    demoUrl: 'https://jefriuprak1.ct.ws/'
  }
])
</script>

<style scoped>
.project-card {
  perspective: 1000px;
}

.hover-card {
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  border: none;
  position: relative;
  overflow: hidden;
}

.hover-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(45deg, rgba(0,123,255,0.1), rgba(0,255,136,0.1));
  opacity: 0;
  transition: opacity 0.3s ease;
}

.hover-card:hover {
  transform: translateY(-10px) rotateX(5deg);
  box-shadow: 0 15px 25px rgba(0,0,0,0.3);
}

.hover-card:hover::before {
  opacity: 1;
}

.card-icon {
  position: absolute;
  top: 1rem;
  right: 1rem;
  font-size: 1.5rem;
  color: #007bff;
  opacity: 0.8;
  transition: all 0.3s ease;
}

.hover-card:hover .card-icon {
  transform: rotate(20deg) scale(1.2);
  color: #00ff88;
}

.project-links {
  margin-top: 1.5rem;
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.3s ease;
}

.hover-card:hover .project-links {
  opacity: 1;
  transform: translateY(0);
}

.btn {
  transition: all 0.3s ease;
  border-width: 2px;
}

.btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}

/* Menggunakan style title yang sama dengan About */
.title-container {
  position: relative;
  display: flex;
  justify-content: center;
}

.section-title {
  position: relative;
  display: inline-flex;
  align-items: center;
  overflow: hidden;
  transition: all 0.3s ease;
  border: 2px solid transparent;
}

.title-icon {
  font-size: 1.5rem;
  opacity: 0.9;
}

.title-underline {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0;
  height: 3px;
  background: linear-gradient(90deg, #007bff, #00ff88);
  transition: width 0.3s ease;
}

.section-title:hover .title-underline {
  width: 100%;
}

.project-image {
  height: 200px;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.hover-card:hover .project-image {
  transform: scale(1.05);
}


.project-links {
  position: relative;
  z-index: 2;
}
</style>