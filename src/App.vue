<template>
  <div id="app">
    <body>
      <div class="container">
        <transition name="show">
            <modal
              v-show="showModal"
              class="is-active"
              :details="detailsModal"
              @clickCloseModal="isClosingModal"/>
        </transition>
        <div class="columns">
          <div class="column is-full has-text-centered">
            <p class="title-report is-size-3-desktop is-size-5-touch">Información de Población censada en Chile al 2024 por sexo y edad</p>
            <p class="is-size-4-desktop is-size-6-mobile">(Datos obtenidos de https://censo2024.ine.gob.cl/)</p>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full has-text-justified">
            <p class="intro-report is-size-4-desktop is-size-6-mobile">
              Esta interfaz permite recorrer rápidamente los datos de la población censada en Chile el año 2024, detallando la distribución por sexo y tramos de edad. Esta información ha sido organizada por regiones, provincias y comunas.
            </p>
          </div>
        </div>
        <div class="columns is-vcentered">
          <div class="column is-1 is-hidden-touch">
            <figure class="image">
              <img src="./assets/chile.png">
            </figure>
          </div>
          <div class="column is-10-desktop is-12-touch">
            <div class="container">
              <div class="columns">
                <div class="column is-10-desktop is-offset-1-desktop has-text-justified">
                  <p class="text-panel is-size-4-desktop is-size-6-mobile">
                    El total de población censada en el año 2024 alcanzó las $18.480.432.- personas, siendo de estas un <strong>51,5% Mujeres</strong> (9.513.399.-) y un <strong>48,5% Hombres</strong> (8.967.033.-). Las región con mayor población es la Metropolitana, seguida por Valparaíso, Biobío y Maule. En la tabla de abajo podrás ver las cantidades por cada región.
                  </p>
                  <iframe class="one" src="https://lookerstudio.google.com/embed/reporting/1673caeb-c758-48e4-a89a-296127a07375/page/n8sTF" frameborder="0" style="border:0" allowfullscreen sandbox="allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox"></iframe>
                </div>
              </div>
            </div>
          </div>
          <div class="column is-1 is-hidden-touch">
            <figure class="image">
              <img src="./assets/chile.png">
            </figure>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full">
            <p class="text-panel is-size-4-desktop is-size-6-mobile">
              En este siguiente panel interactivo podrás conocer las distribuciones del país y regionales <strong>(seleccionar región)</strong>, en términos de rango etario y por sexo.
            </p>
            <iframe class="two" src="https://lookerstudio.google.com/embed/reporting/8a07c854-fe88-412d-b5a3-21ee105757be/page/n8sTF" frameborder="0" style="border:0" allowfullscreen sandbox="allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox"></iframe>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full">
            <p class="text-panel is-size-4-desktop is-size-6-mobile">
              El siguiente panel interactivo muestra la distribución de personas por provincia para las distintas regiones <strong>(seleccionar región)</strong>, además de cantidad de mujeres, hombres y totales censados por provincia.
            </p>
            <iframe class="three" src="https://lookerstudio.google.com/embed/reporting/813caf87-d05b-4e45-ac3b-ce5a2b707d17/page/n8sTF" frameborder="0" style="border:0" allowfullscreen sandbox="allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox"></iframe>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full">
            <p class="text-panel is-size-4-desktop is-size-6-mobile">
              Finalmente puedes revisar los datos específicos a cada región, seleccionando el botón respectivo más abajo El alcance de estos datos regionales es hasta sus comunas.
            </p>
          </div>
        </div>
        <div class="columns">
          <div class="column is-4 button-container">
            <p class="zone is-size-4-desktop is-size-6-mobile">
              <strong>Norte</strong>
            </p>
            <button
              id="1"
              class="button is-rounded"
              @click="clickRegion">
              Arica y Parinacota</button>
            <button
              id="2"
              class="button is-rounded"
              @click="clickRegion">
              Tarapacá</button>
            <button
              id="3"
              class="button is-rounded"
              @click="clickRegion">
              Antofagasta</button>
            <button
              id="4"
              class="button is-rounded"
              @click="clickRegion">
              Atacama</button>
            <button
              id="5"
              class="button is-rounded"
              @click="clickRegion">
              Coquimbo</button>
          </div>
          <div class="column is-4 button-container">
            <p class="zone is-size-4-desktop is-size-6-mobile">
              <strong>Centro</strong>
            </p>
            <button
              id="6"
              class="button is-rounded"
              @click="clickRegion">
              Valparaíso</button>
            <button
              id="7"
              class="button is-rounded"
              @click="clickRegion">
              Metropolitana</button>
            <button
              id="8"
              class="button is-rounded"
              @click="clickRegion">
              Libertador Bernardo O'Higgins</button>
            <button
              id="9"
              class="button is-rounded"
              @click="clickRegion">
              Maule</button>
            <button
              id="10"
              class="button is-rounded"
              @click="clickRegion">
              Ñuble</button>
            <button
              id="11"
              class="button is-rounded"
              @click="clickRegion">
              Biobío</button>
          </div>
          <div class="column is-4 button-container">
            <p class="zone is-size-4-desktop is-size-6-mobile">
              <strong>Sur</strong>
            </p>
            <button
              id="12"
              class="button is-rounded"
              @click="clickRegion">
              La Araucanía</button>
            <button
              id="13"
              class="button is-rounded"
              @click="clickRegion">
              Los Ríos</button>
            <button
              id="14"
              class="button is-rounded"
              @click="clickRegion">
              Los Lagos</button>
            <button
              id="15"
              class="button is-rounded"
              @click="clickRegion">
              Aysen del General Carlos Ibáñez del Campo</button>
            <button
              id="16"
              class="button is-rounded"
              @click="clickRegion">
              Magallanes y de la Antártica Chilena</button>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full has-text-justified">
            <p class="text-panel is-size-4-desktop is-size-6-mobile">
              Hoy, presentar datos ya no basta. La diferencia está en cómo los conectamos con las personas. Muchos profesionales pueden construir dashboards, pero yo ofrezco algo distinto: <strong>interfaces web personalizadas, diseñadas para informar, guiar y cautivar</strong>.<br/><br/>
              Este enfoque supera ampliamente los formatos más tradicionales como los dashboards estáticos o las presentaciones en PowerPoint. ¿Por qué?<br/><br/>
              <strong>- Mayor interacción: </strong>El usuario no es un espectador pasivo, sino que puede explorar la información, comparar y descubrir insights por sí mismo.<br/><br/>
              <strong>- Contexto: </strong>Es posible incorporar explicaciones, anotaciones o guías que acompañen al usuario en la lectura de los datos.<br/><br/>
              <strong>- Escalabilidad y reutilización: </strong>Las interfaces web se pueden actualizar con nuevos datos o funcionalidades sin rehacer el trabajo desde cero.<br/><br/>
              <strong>- Versatilidad:  </strong>Se adaptan a distintos públicos, dispositivos y necesidades de comunicación.<br/><br/>
              Este proyecto no solo muestra lo que sé hacer, sino cómo pienso: buscar siempre nuevas formas de comunicar datos, unir disciplinas y diseñar soluciones útiles, claras y efectivas.
            </p>
          </div>
        </div>
      </div>
    </body>  
    <footer class="footer">
      <div class="content has-text-centered">
        <p>Copyright © desarrollado por Cristian Castillo - 2025</p>
      </div>
    </footer>
  </div>
</template>

<script>

import Modal from './shared/Modal.vue'

export default { 

  name: 'App',

  components: { Modal },

  data () {
    return {

      showModal: false,
      detailsModal: {
        name: '',
        src: ''
      },
      
      regions: [
        {
          id: 1,
          name: 'Arica y Parinacota',
          src: 'https://lookerstudio.google.com/embed/reporting/b7da3ebe-cc67-4c20-b46b-62292290a594/page/n8sTF'
        },
        {
          id: 2,
          name: 'Tarapacá',
          src: 'https://lookerstudio.google.com/embed/reporting/2bafc272-1b23-4430-aec8-0ddc8eba3a77/page/n8sTF'
        },
        {
          id: 3,
          name: 'Antofagasta',
          src: 'https://lookerstudio.google.com/embed/reporting/55ca4ae5-6095-40e3-ae4b-a2114fe38ed7/page/n8sTF'
        },
        {
          id: 4,
          name: 'Atacama',
          src: 'https://lookerstudio.google.com/embed/reporting/b407435a-e4a5-4e41-a72c-c7771513e134/page/n8sTF'
        },
        {
          id: 5,
          name: 'Coquimbo',
          src: 'https://lookerstudio.google.com/embed/reporting/c3501779-bbbe-4c96-9a47-c9f4c6ec5f69/page/n8sTF'
        },
        {
          id: 6,
          name: 'Valparaíso',
          src: 'https://lookerstudio.google.com/embed/reporting/7b75676b-2b74-46b2-b758-caf6f445529c/page/n8sTF'
        },
        {
          id: 7,
          name: 'Metropolitana',
          src: 'https://lookerstudio.google.com/embed/reporting/df8afd5d-046c-40ca-aec1-d4fe0f5d24a8/page/n8sTF'
        },
        {
          id: 8,
          name: 'Libertador Bernardo O´Higgins',
          src: 'https://lookerstudio.google.com/embed/reporting/789516ad-1bad-4214-a0fc-f58a9aea3b8f/page/n8sTF'
        },
        {
          id: 9,
          name: 'Maule',
          src: 'https://lookerstudio.google.com/embed/reporting/f8aaaa8b-157b-4db4-8bd7-f8e72d2fb913/page/n8sTF'
        },
        {
          id: 10,
          name: 'Ñuble',
          src: 'https://lookerstudio.google.com/embed/reporting/3b2a3853-519c-48ff-97fd-07fe909b1b2b/page/n8sTF'
        },
        {
          id: 11,
          name: 'Biobío',
          src: 'https://lookerstudio.google.com/embed/reporting/a1256e60-44fd-4df9-b7b1-7a8992bb62dc/page/n8sTF '
        },
        {
          id: 12,
          name: 'La Araucanía',
          src: 'https://lookerstudio.google.com/embed/reporting/111f82b4-859b-4e68-a9cf-db18aad5253a/page/n8sTF'
        },
        {
          id: 13,
          name: 'Los Ríos',
          src: 'https://lookerstudio.google.com/embed/reporting/a9f917e4-96b8-4d4e-8d69-bb1e66138d92/page/n8sTF'
        },
        {
          id: 14,
          name: 'Los Lagos',
          src: 'https://lookerstudio.google.com/embed/reporting/266ce2d1-bb77-46bc-9787-d4587d1e9b57/page/n8sTF'
        },
        {
          id: 15,
          name: 'Aysen del General Carlos Ibáñez del Campo',
          src: 'https://lookerstudio.google.com/embed/reporting/c0d709d4-03e8-4ea2-a622-f4a8a34db84a/page/n8sTF'
        },
        {
          id: 16,
          name: 'Magallanes y de la Antártica Chilena',
          src: 'https://lookerstudio.google.com/embed/reporting/5a30158e-e47d-4180-981a-2b4626a5c772/page/n8sTF'
        }
      ]
      
    }
  },

  
  methods: {

    isClosingModal () {
      this.showModal = false
      setTimeout(() => {
        this.detailsModal.name = ''
        this.detailsModal.src = ''
      }, 900)
    },

    clickRegion (ev) {
      ev.preventDefault()
      const target = ev.target.id
      
      document.getElementById(target).style.boxShadow = "0px 6px 6px 0px #3C76BA"
      
      setTimeout(() => {
        document.getElementById(target).style.boxShadow = "0px 12px 6px -3px #3C76BA"
      }, 300)

      for (var r in this.regions) {
        if (this.regions[r].id == target) {
          this.detailsModal.name = this.regions[r].name
          this.detailsModal.src = this.regions[r].src
          setTimeout(() => {
            this.showModal = true
          }, 600)
        }
      }
    }
    
  }

}

</script>

<style lang="scss">

@import "./scss/main.scss";

#app {
  font-family: Montserrat, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

body {
  font-size: 15px;
}

.modal {
  margin: 0 auto;
}

.title-report {
  margin-top: 2.1rem;
}

.intro-report {
  margin-bottom: 2.1rem;
}

.one {
  margin-top: 1.5rem;
  margin-bottom: 4.5rem;
  width: 100%;
  aspect-ratio: 100 / 68.4;
}

.two {
  margin: 1.5rem 15% 4.5rem 15%;
  width: 70%;
  aspect-ratio: 100 / 76.7;
}

.three {
  margin: 1.5rem 15%;
  width: 70%;
  aspect-ratio: 100 / 73;
}

.button-container {
  margin-top: 1.5rem;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  flex-direction: column;
}

.zone {
  margin-bottom: 1.5rem;
}

.button {
  width: 60%;
  overflow: hidden;
  text-overflow: ellipsis;
  display: inline-block;
  white-space: nowrap;
  margin-bottom: 1.2rem;
  background-color: #4FA2FF;
  border-color: #4FA2FF !important;
  color: #fff;
  box-shadow: 0px 6px 6px 0px #3C76BA;
  transition: all 300ms;
  -webkit-tap-highlight-color: transparent;
  opacity: .9;
}

.button:hover {
  box-shadow: 0px 12px 6px -3px #3C76BA;
  color: #fff !important;
  opacity: 1;
}

.button:focus {
  color: #fff !important;
}

.footer {
  background-color: #4FA2FF;
  color: #fff;
  margin-top: 3rem;
  padding: 2.4rem 1.5rem;
}

@media screen and (min-width: 769px) and (max-width: 1024px) {

  .title-report {
    margin-left: 3%;
    margin-right: 3%;
    font-weight: bold;
  }

  .intro-report, .text-panel {
    margin-left: 3%;
    margin-right: 3%;
  }

  .one, .two, .three {
    margin: .9rem 1%;
    width: 98%;
  }

  .button {
    box-shadow: 0px 12px 6px -3px #3C76BA;
    transition: all 300ms;
    -webkit-tap-highlight-color: transparent;
    opacity: 1;
  }

  .modal-card {
    width: 90% !important;
  }

}

@media screen and (max-width: 768px) {

  .title-report {
    margin-left: 3%;
    margin-right: 3%;
    font-weight: bold;
  }

  .intro-report, .text-panel {
    margin-left: 3%;
    margin-right: 3%;
  }

  .one, .two, .three {
    margin: .9rem 1%;
    width: 98%;
  }

  .button {
    box-shadow: 0px 12px 6px -3px #3C76BA;
    transition: all 300ms;
    -webkit-tap-highlight-color: transparent;
    opacity: 1;
  }

  .modal-card {
    width: 100% !important;
  }

  .footer {
    padding: 1.5rem;
  }

  .footer p {
    font-size: .81rem;
  }

}

</style>
