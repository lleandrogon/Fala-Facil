<template>
    <AppHeader id="header" />
    <AppHome id="home" />
    <AppCursos id="cursos" />
    <AppMatricula id="matricula" />
    <AppParceria id="parceria" />
    <AppAcademico id="academico" />
    <AppPerguntas id="perguntas" />
    <AppFooter id="footer" />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppHome from './components/AppHome.vue';
import AppCursos from './components/AppCursos.vue';
import AppMatricula from './components/AppMatricula.vue';
import AppParceria from './components/AppParceria.vue';
import AppAcademico from './components/AppAcademico.vue';
import AppPerguntas from './components/AppPerguntas.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  components: {
    AppHeader,
    AppHome,
    AppCursos,
    AppMatricula,
    AppParceria,
    AppAcademico,
    AppPerguntas,
    AppFooter
  }
}
</script>

<style>

</style>
