<template>
<body>
  
  <div class="jumbotron">
    <section class="py-5 text-center border-bottom">
        <div class="row py-lg-5">
          <div class="col-lg-6 col-md-8 mx-auto">
            <h1 class="fw-light">Kirim WA</h1>
            <p class="lead text-muted">Ngirim WA tanpa perlu save.</p>
            <hr>
            <h2 class="fw-light py-2 text-truncate">Tulisin nomor WA-nya dibawah.</h2>
              <div class="px-2">
                  <form action="" class="justify-content-center" @submit.prevent="startChat" id="chatForm">
                      <div class="form-group mb-3">
                          <input type="text" class="form-control border-0 shadow text-center" name="nomor-wa" placeholder="+628.. / 62... / 08..." v-model="nomorWA">
                      </div>
                      <button type="submit" class="btn btn-outline-dark rounded-pill shadow">CHAT!</button>
                  </form>
              </div>
          </div>
        </div>
    </section>

  </div>
</body>
</template>

<script>
export default {
  created () {
      document.title = "Home - Kirim WA";
  },
  data () {
      return {
          nomorWA: '',
          executedWA: '',
      }
  },
  mounted(){

  },
  methods: {
      startChat(){

        if(this.nomorWA.length < 5){
          console.log('inputnya benerin napa')
        } else if (this.nomorWA.charAt(0) == '0'){
          this.executedWA = '62'+this.nomorWA.slice(1)
          window.open('https://web.whatsapp.com/send?phone='+this.executedWA)
        } else {
          this.executedWA = this.nomorWA
          window.open('https://web.whatsapp.com/send?phone='+this.executedWA)
        }
      }
  },
  watch:{
    nomorWA(val){
      this.nomorWA = val.replace(/[^0-9]/g, '')
    }
  }
}
</script>

<style>

</style>
