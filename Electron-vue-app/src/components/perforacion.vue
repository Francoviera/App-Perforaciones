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
      <div class="col-md-12 mb-4 mt-4">
        <!-- Card Start -->
          <div class="card">
            <div class="row ">
              <div class="col-md-7 px-3">
                <small class="text-muted date">{{perforacion.date}}</small>
                <div class="card-block px-6">
                  <h3 class="card-title text-primary">{{perforacion.location}}</h3>
                  <h5 class="card-text">{{perforacion.name}} {{perforacion.surname}}</h5>
                  <p class="card-text">{{perforacion.description}}</p>
                  <div class="div-btns-abm">
                    <button class="btn btn-sm btn-primary ml-2"><i class="fas fa-eye"></i></button>
                    <button class="btn btn-sm btn-warning ml-2"><i class="fas fa-pencil-alt"></i></button>
                    <button class="btn btn-sm btn-danger ml-2"><i class="far fa-trash-alt"></i></button>
                  </div>
                </div>
              </div>
              <!-- Carousel start -->
              <div class="col-md-5">
                <div id="CarouselTest" class="carousel slide" data-ride="carousel">
                  <ol class="carousel-indicators">
                    <li data-target="#CarouselTest" data-slide-to="0" class="active"></li>
                    <!-- <li data-target="#CarouselTest" data-slide-to="1"></li>
                    <li data-target="#CarouselTest" data-slide-to="2"></li> -->
                  </ol>
                  <div class="carousel-inner">
                    <div class="carousel-item active">
                      <img class="d-block imgPerforacion" width="100%" heigth="100%" src="../assets/perforacion.jpg" alt="">
                    </div>
                    <!-- <div class="carousel-item">
                      <img class="d-block" src="https://picsum.photos/450/300?image=855" alt="">
                    </div>
                    <div class="carousel-item">
                      <img class="d-block" src="https://picsum.photos/450/300?image=355" alt="">
                    </div> -->
                    <a class="carousel-control-prev" href="#CarouselTest" role="button" data-slide="prev">
                      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                      <span class="sr-only">Previous</span>
                    </a>
                      <a class="carousel-control-next" href="#CarouselTest" role="button" data-slide="next">
                        <span class="carousel-control-next-icon" aria-hidden="true"></span>
                        <span class="sr-only">Next</span>
                      </a>
                  </div>
                </div>
              </div>
              <!-- End of carousel -->
            </div>
          </div>
          <!-- End of card -->
        </div>
      <!-- </div> -->
    </div>
    <!-- /.row -->
  </div>
</template>

<script>
export default {
  name: 'perforacion',
  props:['perforacion'],
  data(){
    return{
      nombre: '',
    }
  },
  mounted(){
    console.log(this.perforacion);
  }
}
</script>