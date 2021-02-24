<template>
  <div class="home">
    <Perforacion v-for="perforacion of perforaciones" :key="perforacion.id" :perforacion="perforacion"/>
    <footer class="py-5 bg-dark">
      <div class="container">
        <!-- <p class="m-0 text-center text-white">Copyright &copy; Your Website {{fecha}}</p> -->
        <p class="text-white">Copyright © {{fecha}} | Todos los derechos reservados | Esta aplicacion fue realizada <i class="fa fa-fire text-danger" aria-hidden="true"></i> por <a href="https://www.linkedin.com/in/franco-viera-5163ba196/" target="_blank">Franco Viera</a></p>
      </div>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import Perforacion from '@/components/perforacion.vue'

export default {
  name: 'Home',
  components: {
    Perforacion
  },
  data(){
    return{
      fecha: '',
      perforaciones: []

    }
  },
  mounted(){
    this.fecha= new Date().getFullYear();
    let datosDB= JSON.parse(localStorage.getItem('perforaciones'));
    if(datosDB != null){
      this.perforaciones = datosDB;
    }
  },
}
</script>
