<template>
  <main id="app">
    <header>
      <img src="./assets/icon_bnr.png" class="balon-imagen" />
      <span class="texto-cabezera">Copa Qatar 2020</span>
    </header>
    <div id="cuerpo" class="cuerpo">
      <div class="row">
        <div class="col-6 ">
          <span id="cabezera-resultado" class="cabezera-resultado">Resultados</span>
        </div>
        <!-- boton de info de fechas  -->
        <div class="col text-end ">
          <div class="dropdown">
            <button class="btn btn-primary dropdown-toggle" data-bs-toggle="dropdown" type="button"
              id="dropdownMenuButton" aria-haspopup="true" aria-expanded="false">
              Informacion
            </button>
            <div class="dropdown-menu dropdown-menu-dark dropdown-menu-end" aria-labelledby="dropdownMenuButton">
              <a class="dropdown-item" @click="showFecha1()" href="#fecha1"><span class="menu-dd">Fecha1</span></a>
              <a class="dropdown-item" @click="showFecha2()" href="#fecha2"><span class="menu-dd">Fecha2</span></a>
              <a class="dropdown-item" href="#fecha3"><span class="menu-dd">Fecha3</span></a>
              <a class="dropdown-item" href="https://www.youtube.com/" target="_blank"><span
                  class="menu-dd">Fecha4</span></a>
              <a class="dropdown-item" @click="showtablas()" href="#tablas"><span class="menu-dd">Tablas</span></a>
              <a class="dropdown-item" @click="showFechaTodo()" href="#fecha1"><span class="menu-dd">Todo</span></a>
            </div>
          </div>
        </div>
      </div>
      <!-- boton de info de fechas -->
      <div id="fecha1" class="fecha1" v-show="fecha1">
        <br />
        <span class="cabezera-fecha">Fecha 1 </span>
        <!-- boton para editar-->
        <button class="border-0" @click="editandoFecha1()" v-show="!editarFecha1">
          <img src="./assets/1159876.png" class="mb-2" width="30" height="30" />
        </button>
        <!-- esto son los datos que se muestran cuando el numero se pone  -->
        <div v-show="!editarFecha1">
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row ">
                  <span class="nombre-equipos" v-text="partidoLocal1 + ' ' + inpt1"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante1 + ' ' + inpt2"></span>
                </div>
              </div>

              <div class="col-4">
                <span class=""><img src="./assets/resultado1.jpg" class="img-fluid py-4" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal2 + ' ' + inpt3"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante2 + ' ' + inpt4"></span>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado2.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal3 + ' ' + inpt5"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante3 + ' ' + inpt6"></span>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado3.jpeg" class="img-fluid py-4" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal4 + ' ' + inpt7"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante4 + ' ' + inpt8"></span>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado4.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal5 + ' ' + inpt9"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante5 + ' ' + inpt10"></span>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado5.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
        </div>
        <!-- esto son los datos que se muestran cuando se unde el boton de editar , y da la opcion de edidar el marcador -->
        <div v-show="editarFecha1">
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">

                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoLocal1" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt1" />
                  </div>
                </div>
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoVisitante1" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt2" />
                  </div>
                </div>
              </div>

              <div class="col-4">
                <span class=""><img src="./assets/resultado1.jpg" class="img-fluid py-4" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoLocal2" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt3" />
                  </div>
                </div>
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoVisitante2" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt4" />
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado2.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoLocal3" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt5" />
                  </div>
                </div>
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoVisitante3" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt6" />
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado3.jpeg" class="img-fluid py-4" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoLocal4" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt7" />
                  </div>
                </div>
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoVisitante4" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt8" />
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado4.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoLocal5" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt9" />
                  </div>
                </div>
                <div class="row">
                  <div class="">
                    <input class="input-resultado" v-model="partidoVisitante5" />&nbsp<input type="text"
                      class="input-resultado-equipos" v-model="inpt10" />
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado5.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
        </div>
        <!--  -->
        <div class="col text-center">
          <button class="btn btn-primary" @click="enviarFecha1()" type="button">
            Enviar
          </button>
        </div>
      </div>
      <br />
      <!--  -->
      <div id="fecha2" class="fecha2" v-show="fecha2">
        <br />
        <span class="cabezera-fecha">Fecha 2</span>
        <button class="border-0" @click="editandoFecha2()" v-show="!editarFecha2">
          <img src="./assets/1159876.png" class="mb-2" width="30" height="30" />
        </button>
        <div v-show="!editarFecha2">
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal6 + equipo10"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante6 + equipo3"></span>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado6.jpg" class="img-fluid py-4" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal7 + equipo4"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante7 + equipo5"></span>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado7.jpg " class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal8 + equipo8"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante8 + equipo2"></span>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado8.jpg" class="img-fluid" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal9 + equipo1"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante9 + equipo9"></span>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado9.jpg" class="img-fluid" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoLocal10 + equipo6"></span>
                </div>
                <div class="row">
                  <span class="nombre-equipos" v-text="partidoVisitante10 + equipo7"></span>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado10.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
        </div>
        <div v-show="editarFecha2">
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoLocal6"><span
                      class="nombre-equipos" v-text="equipo10"></span>
                  </div>
                </div>
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoVisitante6"><span
                      class="nombre-equipos" v-text="equipo3"></span>
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado6.jpg" class="img-fluid py-4" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoLocal7"><span
                      class="nombre-equipos" v-text="equipo4"></span>
                  </div>
                </div>
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoVisitante7"><span
                      class="nombre-equipos" v-text="equipo5"></span>
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado7.jpg " class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoLocal8"><span
                      class="nombre-equipos" v-text="equipo8"></span>
                  </div>
                </div>
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoVisitante8"><span
                      class="nombre-equipos" v-text="equipo2"></span>
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado8.jpg" class="img-fluid" /></span>
              </div>
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoLocal9"><span
                      class="nombre-equipos" v-text="equipo1"></span>
                  </div>
                </div>
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoVisitante9"><span
                      class="nombre-equipos" v-text="equipo9"></span>
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span><img src="./assets/resultado9.jpg" class="img-fluid" /></span>
              </div>
            </div>
          </div>
          <div class="resultados container-fluid g-0">
            <div class="row g-0">
              <div class="col-2 align-self-center g-0">
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoLocal10"><span
                      class="nombre-equipos" v-text="equipo6"></span>
                  </div>
                </div>
                <div class="row">
                  <div>
                    <input class="input-resultado" type="number" min='0' v-model="partidoVisitante10"><span
                      class="nombre-equipos" v-text="equipo7"></span>
                  </div>
                </div>
              </div>
              <div class="col-4">
                <span class=""><img src="./assets/resultado10.jpg" class="img-fluid py-4" /></span>
              </div>
            </div>
          </div>
        </div>
        <div class="col text-center">
          <button class="btn btn-primary" @click="enviarFecha2()">
            Enviar
          </button>
        </div>
      </div>
      <br />
      <!--  -->
      <div id="fecha3" class="fecha3" v-show="fecha3">
        <br />
        <span class="cabezera-fecha">Fecha 3</span>
        <div class="resultados container-fluid g-0">
          <div class="row g-0">
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo10"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="3 + equipo4"></span>
              </div>
            </div>
            <div class="col-4">
              <span class=""><img src="./assets/resultado11.jpg" class="img-fluid py-4" /></span>
            </div>
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="1 + equipo3"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="1 + equipo2"></span>
              </div>
            </div>
            <div class="col-4">
              <span><img src="./assets/resultado12.jpg" class="img-fluid py-4" /></span>
            </div>
          </div>
        </div>
        <div class="resultados container-fluid g-0">
          <div class="row g-0">
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="0 + equipo7"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="3 + equipo5"></span>
              </div>
            </div>
            <div class="col-4">
              <span class=""><img src="./assets/resultado13.jpg" class="img-fluid" /></span>
            </div>
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo6"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="0 + equipo1"></span>
              </div>
            </div>
            <div class="col-4">
              <span><img src="./assets/resultado14.jpg" class="img-fluid" /></span>
            </div>
          </div>
        </div>
        <div class="resultados container-fluid g-0">
          <div class="row g-0">
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="1 + equipo9"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="0 + equipo8"></span>
              </div>
            </div>
            <div class="col-4">
              <span class=""><img src="./assets/resultado15.jpg" class="img-fluid py-4" /></span>
            </div>
          </div>
        </div>
      </div>
      <br />
      <!--  -->
      <div id="fecha4" class="fecha4" v-show="fecha4">
        <br />
        <span class="cabezera-fecha">Fecha 4</span>
        <div class="resultados container-fluid g-0">
          <div class="row g-0">
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="6 + equipo4"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="1 + equipo7"></span>
              </div>
            </div>
            <div class="col-4">
              <span class=""><img src="./assets/resultado16.jpg" class="img-fluid py-4" /></span>
            </div>
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo8"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="1 + equipo6"></span>
              </div>
            </div>
            <div class="col-4">
              <span><img src="./assets/resultado17.jpg" class="img-fluid py-4" /></span>
            </div>
          </div>
        </div>
        <div class="resultados container-fluid g-0">
          <div class="row g-0">
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo2"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo10"></span>
              </div>
            </div>
            <div class="col-4">
              <span class=""><img src="./assets/resultado18.jpg" class="img-fluid" /></span>
            </div>
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="0 + equipo5"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo9"></span>
              </div>
            </div>
            <div class="col-4">
              <span><img src="./assets/resultado19.jpg" class="img-fluid" /></span>
            </div>
          </div>
        </div>
        <div class="resultados container-fluid g-0">
          <div class="row g-0">
            <div class="col-2 align-self-center g-0">
              <div class="row">
                <span class="nombre-equipos" v-text="0 + equipo1"></span>
              </div>
              <div class="row">
                <span class="nombre-equipos" v-text="2 + equipo3"></span>
              </div>
            </div>
            <div class="col-4">
              <span class=""><img src="./assets/resultado20.jpg" class="img-fluid py-4" /></span>
            </div>
          </div>
        </div>
      </div>
    </div>

  </main>
</template>

<script >


export default {
  created() {

    this.partidoLocal1 = (localStorage.getItem('partidoLocal1')),
      this.partidoVisitante1 = (localStorage.getItem('partidoVisitante1')),
      this.partidoLocal2 = (localStorage.getItem('partidoLocal2')),
      this.partidoVisitante2 = (localStorage.getItem('partidoVisitante2')),
      this.partidoLocal3 = (localStorage.getItem('partidoLocal3')),
      this.partidoVisitante3 = (localStorage.getItem('partidoVisitante3')),
      this.partidoLocal4 = (localStorage.getItem('partidoLocal4')),
      this.partidoVisitante4 = (localStorage.getItem('partidoVisitante4')),
      this.partidoLocal5 = (localStorage.getItem('partidoLocal5')),
      this.partidoVisitante5 = (localStorage.getItem('partidoVisitante5')),
      this.partidoLocal6 = (localStorage.getItem('partidoLocal6')),
      this.partidoVisitante6 = (localStorage.getItem('partidoVisitante6')),
      this.partidoLocal7 = (localStorage.getItem('partidoLocal7')),
      this.partidoVisitante7 = (localStorage.getItem('partidoVisitante7')),
      this.partidoLocal8 = (localStorage.getItem('partidoLocal8')),
      this.partidoVisitante8 = (localStorage.getItem('partidoVisitante8')),
      this.partidoLocal9 = (localStorage.getItem('partidoLocal9')),
      this.partidoVisitante9 = (localStorage.getItem('partidoVisitante9')),
      this.partidoLocal10 = (localStorage.getItem('partidoLocal10')),
      this.partidoVisitante10 = (localStorage.getItem('partidoVisitante10')),
      this.inpt1 = (localStorage.getItem('inpt1')),
      this.inpt2 = (localStorage.getItem('inpt2')),
      this.inpt3 = (localStorage.getItem('inpt3')),
      this.inpt4 = (localStorage.getItem('inpt4')),
      this.inpt5 = (localStorage.getItem('inpt5')),
      this.inpt6 = (localStorage.getItem('inpt6')),
      this.inpt7 = (localStorage.getItem('inpt7')),
      this.inpt8 = (localStorage.getItem('inpt8')),
      this.inpt9 = (localStorage.getItem('inpt9')),
      this.inpt10 = (localStorage.getItem('inpt10'))

  },
  data() {
    const equipo1 = ' Peru ';
    const equipo2 = " Paraguay ";
    const equipo3 = " Argentina ";
    const equipo4 = " Ecuador ";
    const equipo5 = " Uruguay ";
    const equipo6 = " Chile ";
    const equipo7 = " Colombia ";
    const equipo8 = " Venezuela ";
    const equipo9 = " Brazil ";
    const equipo10 = " Bolivia ";
    const fecha1 = true;
    const fecha2 = true;
    const fecha3 = true;
    const fecha4 = true;
    const editarFecha1 = true;
    const editarFecha2 = true;
   


    return {
      equipo1,
      equipo2,
      equipo3,
      equipo4,
      equipo5,
      equipo6,
      equipo7,
      equipo8,
      equipo9,
      equipo10,
      fecha1,
      fecha2,
      fecha3,
      fecha4,
      editarFecha1,
      editarFecha2,
      

    };
  },
  methods: {

    showFecha1() {
      this.fecha1 = true;
      this.fecha2 = false;
      this.fecha3 = false;
      this.fecha4 = false;
    },
    showFecha2() {
      this.fecha1 = false;
      this.fecha2 = true;
      this.fecha3 = true;
      this.fecha4 = false;
    },
    showFechaTodo() {
      this.fecha1 = true;
      this.fecha2 = true;
      this.fecha3 = true;
      this.fecha4 = true;
    },
    editandoFecha1() {
      this.editarFecha1 = true;
    },
    enviarFecha1() {
      this.editarFecha1 = false;
      localStorage.setItem('partidoLocal1', (this.partidoLocal1)),
        localStorage.setItem('partidoVisitante1', (this.partidoVisitante1)),
        localStorage.setItem('partidoLocal2', (this.partidoLocal2)),
        localStorage.setItem('partidoVisitante2', (this.partidoVisitante2)),
        localStorage.setItem('partidoLocal3', (this.partidoLocal3)),
        localStorage.setItem('partidoVisitante3', (this.partidoVisitante3)),
        localStorage.setItem('partidoLocal4', (this.partidoLocal4)),
        localStorage.setItem('partidoVisitante4', (this.partidoVisitante4)),
        localStorage.setItem('partidoLocal5', (this.partidoLocal5)),
        localStorage.setItem('partidoVisitante5', (this.partidoVisitante5)),
        localStorage.setItem('inpt1', (this.inpt1)),
        localStorage.setItem('inpt2', (this.inpt2)),
        localStorage.setItem('inpt3', (this.inpt3)),
        localStorage.setItem('inpt4', (this.inpt4)),
        localStorage.setItem('inpt5', (this.inpt5)),
        localStorage.setItem('inpt6', (this.inpt6)),
        localStorage.setItem('inpt7', (this.inpt7)),
        localStorage.setItem('inpt8', (this.inpt8)),
        localStorage.setItem('inpt9', (this.inpt9)),
        localStorage.setItem('inpt10', (this.inpt10))

    },
    editandoFecha2() {
      this.editarFecha2 = true;
    },
    enviarFecha2() {
      this.editarFecha2 = false;
      localStorage.setItem('partidoLocal6', (this.partidoLocal6)),
        localStorage.setItem('partidoVisitante6', (this.partidoVisitante6)),
        localStorage.setItem('partidoLocal7', (this.partidoLocal7)),
        localStorage.setItem('partidoVisitante7', (this.partidoVisitante7)),
        localStorage.setItem('partidoLocal8', (this.partidoLocal8)),
        localStorage.setItem('partidoVisitante8', (this.partidoVisitante8)),
        localStorage.setItem('partidoLocal9', (this.partidoLocal9)),
        localStorage.setItem('partidoVisitante9', (this.partidoVisitante9)),
        localStorage.setItem('partidoLocal10', (this.partidoLocal10)),
        localStorage.setItem('partidoVisitante10', (this.partidoVisitante10))

    },

  },
};


</script>

<style>
.border-0 {
  background-color: white;
}

.menu-dd {
  color: white;
  font-weight: 500;
}

.img-fluid {
  height: 100%;
  width: 90%;
}

.nombre-equipos {
  font-weight: 700;
  font-size: 24px;


}

.input-resultado-equipos {
  font-weight: 700;
  font-size: 24px;
  text-align: center;
  width: 70%;
  margin-top: 10px;


}

.input-resultado {
  font-weight: 700;
  font-size: 24px;
  width: 15%;
  text-align: center;
}

/* el span de todos es fecha 1  */
.cabezera-fecha {
  color: blue;
  font-weight: 900;
  font-size: 24px;
}

.cabezera-resultado {
  color: blue;
  font-weight: 900;
  font-size: 32px;
  text-align: end;
}

.texto-cabezera {
  color: white;
  font-weight: 900;
  font-size: 32px;
}

.cuerpo {
  /* es el padding entre el header y lo que voy a escribir */
  padding: 30px 15px;
}

main {
  background-color: white;
}

body {
  background-color: lightgray !important;
  width: 90%;
  margin: 0 auto !important;
}

header {
  background-image: url(./assets/background_bnr.png);
  border-radius: 0px 0px 15px 15px;
  border: none;
  background-size: 100% 100%;
  /* estas 2 son muy importantes para que tenga un texto centrado  */
  display: flex;
  align-items: center;
}

.balon-imagen {
  height: 6rem;
  margin-top: 10px;
  margin-bottom: 10px;
}

@media screen and (max-width: 943px) {
  .nombre-equipos {
    font-size: 60%;
  }
}

@media screen and (max-width: 391px) {
  .nombre-equipos {
    font-size: 52%;
  }
}
</style>
<!-- npm run dev -->
