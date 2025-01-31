<template>
    <AppHeader />
    <AppHome />
    <AppCursos />
    <AppMatricula />
    <AppParceria />
    <AppAcademico />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppHome from './components/AppHome.vue';
import AppCursos from './components/AppCursos.vue';
import AppMatricula from './components/AppMatricula.vue';
import AppParceria from './components/AppParceria.vue';
import AppAcademico from './components/AppAcademico.vue';

export default {
  components: {
    AppHeader,
    AppHome,
    AppCursos,
    AppMatricula,
    AppParceria,
    AppAcademico
  }
}
</script>

<style>

</style>
