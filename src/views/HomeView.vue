<template>
  <div>
    <header class="Encabezado">
      <menu class="Opciones">
        <li>EMISORAS</li>
        <li>PODCASTS</li>
        <li>MI LISTA</li>
        <li>BUSQUEDA</li>
      </menu>
    </header>

    <main class="Contenido">
      <section class="componente_1">
        <EmisoraImagenes></EmisoraImagenes>
      </section>  
      <section class="componente_2">
        <ListaEmisora></ListaEmisora>
      </section>  
    </main>
    <footer class="footer">
            @diseño web || CBN 2024. Reservados Todos los derechos
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
import EmisoraImagenes from '/src/components/EmisoraImagenes';
import ListaEmisora from '@/components/ListaEmisora.vue';

export default {
  name: 'HomeView',
  components: {
    EmisoraImagenes,
    ListaEmisora
  }
}
</script>

<style>
  .Encabezado{
    background: #455A64;
    color: white;
    width: 100%;
    height: 80px;
  }

  .Opciones{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-around;
    text-align: center;
    align-items: center;
  }

  .Opciones li{
    list-style: none;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .Opciones li:hover{
    cursor: pointer;
    border-bottom: 3px white solid;
  }

  .Contenido{
    width: 100%;
    height: 100%;
    display: flex;
  }

  .componente_1{
    width: 70%;
    height: 600px;
  }

  .componente_2{
    width: 30%;
    height: 600px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    background:#21404B;
    list-style: none;
  }
  .footer{
    width: 100%;
    height: 50px;
    background: #455A64;
    color: #C8CED1 ;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
