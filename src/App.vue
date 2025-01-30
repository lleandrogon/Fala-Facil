<template>
    <AppHeader />
    <AppHome />
    <AppCursos />
    <AppMatricula />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppHome from './components/AppHome.vue';
import AppCursos from './components/AppCursos.vue';
import AppMatricula from './components/AppMatricula.vue';

export default {
  components: {
    AppHeader,
    AppHome,
    AppCursos,
    AppMatricula
  }
}
</script>

<style>

</style>
