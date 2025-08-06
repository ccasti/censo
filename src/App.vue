<template>
  <div id="app">
    <body>
      <div class="container">
        <div class="columns">
          <div class="column is-full has-text-centered">
            <p class="title-report is-size-3-desktop is-size-6-mobile">Análisis de Compras realizadas en el período entre enero 2023 y junio 2025</p>
            <p class="is-size-4-desktop is-size-6-mobile">(Datos obtenidos del registro de compras de sii)</p>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full has-text-justified">
            <p class="info is-size-4-desktop is-size-6-mobile">El siguiente cuadro de información muestra el total de las compras realizadas en los años 2023, 2024 y hasta junio de 2025. En el gráfico, al posicionar tu cursor sobre el mes respectivo (o haciendo tap si estas en un dispositivo touch), podrás ver la información de compras del mes, por cada año.</p>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full">
            <iframe class="one" src="https://lookerstudio.google.com/embed/reporting/6165e4fa-d92a-4f82-93e6-ba3fc884443e/page/lCbTF" frameborder="0" style="border:0" allowfullscreen sandbox="allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox"></iframe>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full has-text-justified">
            <p class="info is-size-4-desktop is-size-6-mobile">El siguiente cuadro muestra el listado de los 10 proveedores más importantes en función del volumen de compras totales del período. Del listado de proveedores ubicado a la izquierda del panel, puedes seleccionar un proveedor en particular para ver las compras realizadas en los años de información y al igual que en panel anterior, puedes posicionarte en el mes respectivo para ver los valores graficados.</p>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full">
            <iframe class="two" src="https://lookerstudio.google.com/embed/reporting/b5361ddb-3e18-4cda-9351-f872cdcc62d5/page/qoiTF" frameborder="0" style="border:0" allowfullscreen sandbox="allow-storage-access-by-user-activation allow-scripts allow-same-origin allow-popups allow-popups-to-escape-sandbox"></iframe>
          </div>
        </div>
        <div class="columns">
          <div class="column is-full has-text-justified">
            <p class="info is-size-4-desktop is-size-6-mobile">Esta forma de presentación de la información, que combina las posibilidades de visualización de información que entregan las herramientas como PowerBI, Data Studio de google o Tableau, con las infinitas posibilidades del desarrollo web, permitiendo generar presentaciones personalizadas y dinámicas, ideales para presentaciones a directorios y/o equipos de trabajo, facilitando la comprensión y toma de decisiones.</p>
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

export default { 

  name: 'App',

  data () {
    return { 
      
      
    }
  },

  
  methods: {
    
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

.title-report {
  margin-top: 2.1rem;
}

.info {
  margin-top: 1.8rem;
}

.one {
  margin: 1.5rem 10%;
  width: 80%;
  aspect-ratio: 100 / 65;
}

.two {
  margin: 1.5rem 0;
  width: 100%;
  aspect-ratio: 100 / 43.4;
}


.footer {
  background-color: #CD564A;
  color: #fff;
  margin-top: 3rem;
  padding: 2.4rem 1.5rem;
}

@media screen and (max-width: 768px) {

  .info {
    margin: .9rem .3rem;
  }

  .one, .two {
    margin: .9rem 1%;
    width: 98%;
  }

  .footer {
    padding: 1.5rem;
  }

  .footer p {
    font-size: .81rem;
  }

}

</style>
