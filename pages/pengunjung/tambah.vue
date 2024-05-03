<template>
    <div class="container-fluid">
      <div class="row">
        <div class="col-lg-12">
          <h2 class="text-center my-4">ISI BUKU KUNJUNGAN</h2>
          <form @submit.prevent="kirimData">
            <div class="mb-3">
              <input v-model="form.nama" type="text" class="form-control form-control-lg rounded-5" placeholder="Nama...">
            </div>
            <div class="mb-3">
              <select v-model="form.keanggotaan" class="keanggotaan form-control-lg form-select rounded-5">
                <option value="">Keanggotaan</option>
                <option v-for="(member, i) in members" :key="i" :value="member.id">{{ member.nama }}</option>
              </select>
            </div>
            <div v-if="form.keanggotaan == 2" class="mb-3">
              <div class="row">
                <div class="col-md-4">
                  <select v-model="form.tingkat" class="tingkat form-control-lg form-select rounded-5 mb-2">
                    <option value="">kelas</option>
                    <option value="1">X</option>
                    <option value="2">XI</option>
                    <option value="3">XII</option>
                  </select>
                </div>
                <div class="col-md-4">
                  <select v-model="form.jurusan" class="jurusan form-control-lg form-select rounded-5 mb-2">
                    <option value="">Jurusan</option>
                    <option value="PPLG">PPLG</option>
                    <option value="TJKT">TJKT</option>
                    <option value="TSM">TSM</option>
                    <option value="TOI">TOI</option>
                    <option value="DKV">DKV</option>
                  </select>
                </div>
                <div class="col-md-4">
                  <select v-model="form.kelas" class="form-control form-control-lg form-select rounded-5 mb-2">
                    <option value="">tingkat</option>
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option value="3">3</option>
                    <option value="4">4</option>
                  </select>
                </div>
              </div>
            </div>
            <div class="mb-3">
              <select v-model="form.keperluan" class="form-control form-control-lg form-select rounded-5">
                <option value="">Keperluan</option>
                <option v-for="(item,i) in objectives" :key="i" :value="item.id">{{ item.nama }}</option>
              </select>
            </div>
              <button type="submit" class="btn btn-light btn-lg rounded-5 px-5">KIRIM</button>
          </form>
        </div>
      </div>
    </div>
  </template>

<script setup>
const supabase = useSupabaseClient()

const members = ref([])
const objectives = ref([])
const form =ref({
    nama:"",
    keanggotaan:"",
    tingkat:"",
    jurusan:"",
    kelas:"",
    keperluan:"",
})
const kirimData = async() => {
    const { error } = await supabase.from('pengunjung').insert([form.value])
    if(error) throw error
    else navigateTo('/pengunjung')
}

const getKeanggotaan = async () => {
    const { data,error } = await supabase.from('Keanggotaan').select('*')
    if(data) members.value = data
}

const getkeperluan = async () => {
    const { data, error } = await supabase.from('Keperluan').select('*')
    if(data) objectives.value = data
}

onMounted(() => {
    getKeanggotaan()
    getkeperluan()
})
</script>


<style scoped>
.form-control {
    background-color: #D9D9D9;
}

.form-keanggotaan {
    background-color: #D9D9D9;
}

.btn {
    background-color: #D9D9D9;
}
.form-kelas{
    background-color: #D9D9D9;
}
.form-keperluan{
    background-color: #D9D9D9;
}
.form-jurusan{
    background-color: #D9D9D9;
}
.tingkat{
    background-color: #D9D9D9;
}
.jurusan {
    background-color: #D9D9D9;
}
.keanggotaan {
    background-color: #D9D9D9;
}
</style> 