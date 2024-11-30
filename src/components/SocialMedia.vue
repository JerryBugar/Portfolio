<template>
  <section id="social-media" class="py-5">
    <div class="title-container">
      <h2 class="section-title text-center bg-dark text-white py-3 rounded mx-auto px-5">
        <i class="bi bi-share-fill me-2"></i>
        Media Sosial
        <div class="title-underline"></div>
      </h2>
    </div>
    <div class="d-flex justify-content-center flex-wrap gap-3 mt-4">
      <a href="https://twitter.com/@JefriHakims" class="social-icon">
        <i class="fab fa-twitter"></i>
      </a>
      <a href="https://www.linkedin.com/search/results/all/?fetchDeterministicClustersOnly=true&heroEntityKey=urn%3Ali%3Afsd_profile%3AACoAAFVUfgYB39wa09Irx8_SKpR5It4XNzJWjvM&keywords=jefri%20hakim&origin=RICH_QUERY_TYPEAHEAD_HISTORY&position=0&searchId=544b3f8a-1a38-4aae-81d2-83c72c0a667e&sid=%40.o&spellCorrectionEnabled=true" class="social-icon">
        <i class="fab fa-linkedin"></i>
      </a>
      <a href="https://instagram.com/jfri_a.h" class="social-icon">
        <i class="fab fa-instagram"></i>
      </a>
      <a href="https://github.com/JerryBugar" class="social-icon">
        <i class="fab fa-github"></i>
      </a>
      <a href="https://facebook.com/username" class="social-icon">
        <i class="fab fa-facebook"></i>
      </a>
    </div>
  </section>
</template>

<style scoped>
section {
  margin: 2rem 0;
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

.social-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 50px;  /* ukuran default lebih kecil */
  height: 50px; /* ukuran default lebih kecil */
  border-radius: 50%;
  background: linear-gradient(45deg, #f8f9fa, #e9ecef);
  background-size: 200% 200%;
  animation: gradientAnimation 5s ease infinite;
  color: #fff;
  text-decoration: none;
  transition: all 0.4s ease;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  margin: 5px; /* margin lebih kecil */
  position: relative;
  overflow: hidden;
}

.social-icon:hover {
  transform: translateY(-8px) scale(1.1) rotate(10deg);
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.3);
  background-position: right center;
}

.social-icon i {
  font-size: 1.5rem; /* ukuran font default lebih kecil */
  position: relative;
  z-index: 1;
  transition: all 0.4s ease;
}

.social-icon:hover i {
  color: white;
  transform: scale(1.2) rotate(-10deg);
}

.fa-twitter { color: #1DA1F2; }
.fa-linkedin { color: #0077B5; }
.fa-instagram { color: #E4405F; }
.fa-github { color: #333; }
.fa-facebook { color: #1877F2; }

.title-container {
  position: relative;
  display: flex;
  justify-content: center;
  margin-bottom: 30px;
}

.section-title i {
  font-size: 1.5rem;
  transition: all 0.4s ease;
}

.section-title:hover i {
  transform: rotate(720deg) scale(1.3);
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

/* Tambahkan animasi fade */
.animate__animated {
  animation-duration: 1s;
}

@keyframes gradientAnimation {
  0% { background-position: left center; }
  100% { background-position: right center; }
}

.title-icon {
  font-size: 1.5rem;
  opacity: 0.9;
}

a[href*="twitter"]:hover {
  background: linear-gradient(45deg, #1DA1F2, #0d8bd9);
}

a[href*="linkedin"]:hover {
  background: linear-gradient(45deg, #0077B5, #004d76);
}

a[href*="instagram"]:hover {
  background: linear-gradient(45deg, #833AB4, #FD1D1D, #F77737);
}

a[href*="github"]:hover {
  background: linear-gradient(45deg, #333333, #24292e);
}

a[href*="facebook"]:hover {
  background: linear-gradient(45deg, #1877F2, #0d64d1);
}
</style>