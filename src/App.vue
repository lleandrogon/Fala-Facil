<template>
    <AppHeader />
    <AppHome />
    <AppCursos />
</template>

<script>
import AppHeader from './components/AppHeader.vue';
import AppHome from './components/AppHome.vue';
import AppCursos from './components/AppCursos.vue';

export default {
  components: {
    AppHeader,
    AppHome,
    AppCursos
  }
}
</script>

<style>

</style>
