<script setup>
import CrearUsuario from './components/CrearUsuario.vue';
import ListaUsuarios from './components/ListaUsuarios.vue';
</script>

<template>
  <div class="container">
    <div class="row">
      <!-- Componente para agregar usuarios -->
      <CrearUsuario class="col-12 col-md-6"/>
      <!-- Componente para mostrar la lista de usuarios -->
      <ListaUsuarios class="col-12 col-md-6"/>
    </div>
  </div>
</template>

<style scoped>
</style>
