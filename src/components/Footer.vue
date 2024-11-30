<template>
  <footer class="bg-dark text-white py-4 mt-5">
    <div class="container">
      <div class="row">
        <div class="col-md-4 mb-3 mb-md-0">
          <h5 class="mb-3">Tentang Saya</h5>
          <p class="mb-0">Web developer yang selalu gas pol dalam bikin project keren dan next level! Siap ngoding 24/7 buat wujudin ide-ide fresh kalian! ✨</p>
        </div>
        <div class="col-md-4 mb-3 mb-md-0">
          <h5 class="mb-3">Kontak</h5>
          <p class="mb-1"><i class="bi bi-envelope-fill me-2"></i>jefridocs@gmail.com</p>
          <p class="mb-1"><i class="bi bi-telephone-fill me-2"></i>+62 896-2997-2696</p>
          <p class="mb-1"><i class="bi bi-whatsapp me-2"></i>+62 896-2997-2696</p>
          <p class="mb-0"><i class="bi bi-geo-alt-fill me-2"></i>Bandung, Indonesia</p>
        </div>
        <div class="col-md-4">
          <h5 class="mb-3">Informasi</h5>
          <ul class="list-unstyled">
            <li class="mb-2"><i class="bi bi-clock me-2"></i>Jam sekolah: Senin - Jumat</li>
            <li class="mb-2"><i class="bi bi-clock-fill me-2"></i>06:00 - 16:00 WIB</li>
            <li class="mb-4"><i class="bi bi-envelope-paper-fill me-2"></i>Tersedia saat libur</li>
            <li class="mb-0">&copy; 2024 Muhammad Jefri Alhakim</li>
            <li>All rights reserved.</li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
footer {
  box-shadow: 0 -5px 15px rgba(0, 0, 0, 0.1);
}

h5 {
  color: #007bff;
  font-weight: 600;
  position: relative;
  display: inline-block;
}

h5::after {
  content: '';
  position: absolute;
  left: 0;
  bottom: -5px;
  width: 50px;
  height: 2px;
  background: #007bff;
}

i {
  color: #007bff;
}

p, li {
  font-size: 0.9rem;
  line-height: 1.6;
  transition: all 0.3s ease;
}

p:hover, li:hover {
  transform: translateX(5px);
  color: #007bff;
}

.list-unstyled i {
  font-size: 0.9rem;
}
</style>