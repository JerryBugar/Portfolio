<template>
  <section id="about" class="py-5">
    <div class="title-container mb-4">
      <h2 class="section-title text-center bg-dark text-white py-3 rounded mx-auto px-5">
        <span class="title-icon me-2">
          <i class="bi bi-person-badge-fill"></i>
        </span>
        Tentang Saya
        <div class="title-underline"></div>
      </h2>
    </div>
    <div class="row g-4">
      <div class="col-md-4">
        <div class="card h-100 bg-dark shadow-sm hover-card">
          <div class="card-body">
            <div class="d-flex align-items-center mb-3">
              <div class="card-icon bg-primary text-white rounded-circle me-3">
                <i class="bi bi-person-circle"></i>
              </div>
              <h5 class="card-title mb-0 text-white">Profil</h5>
            </div>
            <p class="card-text bg-light bg-opacity-75 rounded p-3">
              Hai! Perkenalkan nama saya <strong>Muhammad Jefri Alhakim</strong>, 
              saya saat ini berusia <strong>17 Tahun</strong>, lahir di <strong>Bandung</strong>. 
              Saya saat ini bersekolah di <strong>SMK 1 ANGKASA MARGAHAYU</strong> 
              dengan jurusan RPL<strong>[REKAYASA PERANGKAT LUNAK]</strong>.
            </p>
          </div>
        </div>
      </div>
      
      <div class="col-md-4">
        <div class="card h-100 bg-dark shadow-sm hover-card">
          <div class="card-body">
            <div class="d-flex align-items-center mb-3">
              <div class="card-icon bg-success text-white rounded-circle me-3">
                <i class="bi bi-code-slash"></i>
              </div>
              <h5 class="card-title mb-0 text-white">Keahlian</h5>
            </div>
            <p class="card-text bg-light bg-opacity-75 rounded p-3">
              <strong>Saya seorang programmer</strong>, memiliki ketertarikan yang mendalam 
              dalam dunia teknologi dan pengembangan perangkat lunak. Saya memiliki kemampuan 
              untuk cepat belajar dan memahami teknologi baru, serta selalu antusias 
              menghadapi tantangan pemrograman.
            </p>
          </div>
        </div>
      </div>
      
      <div class="col-md-4">
        <div class="card h-100 bg-dark shadow-sm hover-card">
          <div class="card-body">
            <div class="d-flex align-items-center mb-3">
              <div class="card-icon bg-info text-white rounded-circle me-3">
                <i class="bi bi-trophy"></i>
              </div>
              <h5 class="card-title mb-0 text-white">Tujuan</h5>
            </div>
            <p class="card-text bg-light bg-opacity-75 rounded p-3">
              <strong>Tujuan saya menjadi programmer</strong> adalah untuk berkontribusi 
              dalam pengembangan solusi teknologi yang inovatif, mengikuti perkembangan 
              teknologi yang semakin maju, dan mengubah ide-ide kreatif menjadi aplikasi 
              yang bermanfaat bagi masyarakat.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hover-card {
  transition: all 0.3s ease;
  border: none;
}

.hover-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 0.5rem 1rem rgba(0, 0, 0, 0.15) !important;
}

.card-icon {
  position: absolute;
  top: -20px;
  right: -20px;
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.5rem;
  transform: rotate(45deg);
  transition: all 0.3s ease;
}

.hover-card:hover .card-icon {
  transform: rotate(0deg);
}

.card-text {
  position: relative;
  z-index: 1;
  padding-top: 1rem;
}

/* Tambahkan animasi fade */
.animate__animated {
  animation-duration: 1s;
}

@keyframes fadeInLeft {
  from {
    opacity: 0;
    transform: translateX(-100px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(100px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(100px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

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

.section-title:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
  border-color: #007bff;
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
</style>