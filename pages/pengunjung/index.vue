<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
                <div class="my-3">
                    <input type="search" class="form-control form-control-lg rounded-5" placeholder="Filter...">
                </div>
                <div class="my-3 text-muted">MENAMPILKAN 1 DARI 1</div>
                <table class="table">
                    <thead>
                        <tr>
                            <td>No </td>
                            <td>NAMA</td>
                            <td>KEANGGOTAAN</td>
                            <td>WAKTU</td>
                            <td>KEPERLUAN</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1.</td>
                            <td>Zul Hilmi</td>
                            <td>Guru</td>
                            <td>24 Februari 2024,23.31.00</td>
                            <td>Baca</td>
                            
                        </tr>
                        <tr>
                            <td>2.</td>
                            <td>Gina rahma</td>
                            <td>Siswa</td>
                            <td>28 Februari 2024,23.31.00</td>
                            <td>Baca</td>  
                        </tr>
                        <nuxt-link to="/">
        <button type="submit" class="btn btn-light btn-lg rounded-5 px-5">kembali</button></nuxt-link>
                    </tbody>
                </table>
            </div>
        </div>
    </div>
</template>
<style scoped>
.form-control {
    background-color: #D9D9D9;
}
</style>