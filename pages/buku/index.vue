<template>
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <h2 class="text-center my-4">BUKU</h2>
          <div class="my-3">
            <input type="search" class="form-control rounded-5" placeholder="Mau baca apa hari ini?">
          </div>
          <div class="my-3 text-muted">menampilkan 4 dari 125</div>
          <div class="row justify-content-evenly">
            <div class="col-lg-2">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/img/cover2.jpg" class="cover" alt="cover 2">
                </div>
              </div>
            </div>
            <div class="col-lg-2">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/img/cover3.jpg" class="cover" alt="cover3">
                </div>
              </div>
            </div>
            <div class="col-lg-2">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/img/cover4.jpg" class="cover" alt="cover4">
                </div>
              </div>
            </div>
            <div class="col-lg-2">
              <div class="card mb-3">
                <div class="card-body">
                  <img src="~/assets/img/cover5.jpg" class="cover" alt="cover5">
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <nuxt-link to="/">
      <button type="button" class="btn btn-primary">KEMBALI</button></nuxt-link>
    </div>
  </template>
  
  
  <style scoped>
  .card-body {
    width: 100%;
    height: 30em;
    padding: 0;
  }
  .cover {
    width: 100%;
    height: 100%;
    object-fit: cover;
    object-position: 0 30;
  }
  </style>