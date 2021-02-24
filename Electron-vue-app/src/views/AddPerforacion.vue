<template>
  <div>
    <div class="container AddButton">
      <form>
        <div class="form-group">
            <label for="validation01">Nombre</label>
            <input type="text" v-model="name"  :class="{'is-invalid form-control' :  name == '',  'is-valid form-control' :  name != ''}" id="validation01" 
              placeholder="Nombre" required>
        </div>
        <div class="form-group">
            <label for="validation01">Apellido</label>
            <input type="text" v-model="surname"  :class="{'is-invalid form-control' :  surname == '',  'is-valid form-control' :  surname != ''}" id="validation02" 
              placeholder="Apellido" required>
        </div>
        <div class="form-group">
            <label for="validation02">Lugar</label>
            <input type="text" v-model="location"  :class="{'is-invalid form-control' :  location == '',  'is-valid form-control' :  localStorage != ''}" id="validation03" placeholder="Ciudad" required>
        </div>
        <div class="form-group">
            <label for="validation02">Descripcion</label>
            <input type="text" v-model="description"  :class="{'is-invalid form-control' :  description == '',  'is-valid form-control' :  description != ''}" id="validation04" placeholder="Descripcion" required>
        </div>
        <div class="form-group">
            <label for="validation02">Fecha</label>
            <input type="Date" v-model="date"  :class="{'is-invalid form-control' :  date == '',  'is-valid form-control' :  date != ''}"  id="validation04" required>
        </div>
        <div class="col-sm-10">
          <button type="submit" class="btn btn-success" v-on:click="addPerforacion">Agregar</button>
        </div>
      </form>
    </div>
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
import audio from '../electron/audio';

export default {
  name: 'AddPerforacion',
  components: {
  },
  data: function(){
    return{
      cargando: true,
      perforaciones: [],
      date: "",
      description: "",
      name: "",
      surname: "",
      location: "",
      phone: "",
    }
  },
  mounted(){
    this.fecha= new Date().getFullYear();
    // let datosDB= JSON.parse(localStorage.getItem('perforaciones'));
    // if(datosDB != null){
    //   this.perforaciones = datosDB;
    // }
  },
  methods:{
      addPerforacion() {
        if(this.name != "" && this.surname != "" && this.location != "" && this.description != "" && this.date != ""){
          let perforacion= {
            id: this.perforaciones.length,
            name: this.name,
            surname: this.surname,
            description: this.description,
            location: this.location,
            date: this.date
          }
          this.perforaciones.push(perforacion);
          localStorage.setItem('perforaciones', JSON.stringify(this.perforaciones));
          this.name,
          this.surname= "",
          this.description= "",
          this.location= "",
          this.date= ""
        }else{
          alert("Porfavor complete todos los campos del formulario")
        }
      },
      obtenerImagen(e){
          let file= e.target.files[0];
          // console.log(file)
          audio.save(file);
          // this.addButton(file);
      },
    },
}
</script>