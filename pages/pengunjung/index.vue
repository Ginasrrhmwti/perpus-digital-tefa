<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
                <div class="my-3">
                    <form  @submit.prevent="getTotalRiwayat">
                        <input v-model="keyword" type="search" class="form-control rounded-5" placeholder="Filter...">
                    </form>
                </div>
                <div class="my-3 text-muted">menampilkan {{ visitors?.length }} dari {{ totalRiwayat }}</div> 
                 <table class="table">
                    <thead>
                        <tr>
                            <td>No</td>
                            <td>NAMA</td>
                            <td>KEANGGOTAAN</td>
                            <td>WAKTU</td>
                            <td>KEPERLUAN</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="(visitor,i) in visitors" :key="i">
                            <td>{{ i+1 }}.</td>
                            <td>{{ visitor.nama }}</td>
                            <td>{{ visitor.keanggotaan.nama }}</td>
                            <td>{{ visitor.tanggal }}, {{ visitor.waktu }}</td>
                            <td>{{ visitor.keperluan.nama }}</td>
                        </tr>
                    </tbody>
                 </table>
            </div>
        </div>
        <nuxt-link to="/">
        <button type="submit" class="btn btn-light btn-lg rounded-5 px-5">kembali</button></nuxt-link>
    </div>
</template>
<script setup>
const supabase = useSupabaseClient()
const totalRiwayat = ref(0);
const visitors = ref([])
const keyword = ref('')

const getPengunjung = async () => {
    const { data, error } = await supabase.from('pengunjung').select(`*, keanggotaan(*), keperluan(*)`)
    .order('id', { ascending: false })
    if(data) visitors.value = data
}
const getTotalRiwayat = async () => {
  const { count, error } = await supabase
    .from("pengunjung")
    .select(`*, keanggotaan(*), keperluan(*)`, { count: "exact", head: true });
  if (count) totalRiwayat.value = count;
};
onMounted(() => {
    getPengunjung()
    getTotalRiwayat()
})
</script>

<style scoped>
.btn {
    background-color: #D9D9D9;
}
.form-control{
    background-color: #D9D9D9;
}
</style>