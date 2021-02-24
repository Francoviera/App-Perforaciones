<template>
  <div class="container-fluid">
    <div class="row">  
      <div class="col-lg-4 col-md-4 col-sm-4">
        <div class="section-title ">
          <div class="input-group mb-3">
              <div class="input-group-prepend">
                <span class="input-group-text" id="basic-addon1"><i class="fas fa-search"></i></span>
              </div>
              <input type="text" class="form-control" placeholder="Busque Aqui" aria-label="Username" aria-describedby="basic-addon1" v-model="nombre">
            </div>
          </div>
        </div>
      </div>   
    <div class="row">
      <div class="col-md-12 scroll">
        <!-- Blog Post -->
        <div class="col-lg-4 col-md-6 mb-4 mt-4">
            <div class="card h-150 button-div">
            <a href="#"><img class="card-img-top" src="http://placehold.it/700x400" alt=""></a>
              <div class="card-body">
                <h4 class="card-title">
                  <a href="#">Name lugar </a>
                </h4>
                <h5>pClient</h5>
                <p class="card-text">Description</p>
              </div>
              <!-- <div class="card-footer">
                <small class="text-muted">&#9733; &#9733; &#9733; &#9733; &#9734;</small>
              </div> -->
            </div>
        </div>
      </div>
    </div>
    <!-- /.row -->
  </div>
</template>

<script>
export default {
  name: 'perforacion',
  props: {
    
  },
  data(){
    return{
      nombre: '',
    }
  },
  mounted(){
    // var audio = new Audio(require("../assets/audios/2.mp3"));
    // audio.play();
    // audio.pause();
  }
}
</script>