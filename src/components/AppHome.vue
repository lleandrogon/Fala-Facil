<template>
  <div :style="{ backgroundImage: backgroundAtual }" class="container-fluid home"></div>
</template>

<script>
export default {
    name: "AppHome",

    data() {
        return {
        backgrounds: [
            'url("https://wallpapers.com/images/hd/english-2000-x-1333-wallpaper-di44s6r4zq9mj991.jpg")',
            'url("https://www.nexteducacion.com/wp-content/uploads/2024/01/Imagen-Blog-Next-30-1024x535.png")',
            'url("https://circuitomt.com.br/wp-content/uploads/2024/07/unnamed-34-1254x700.jpg")',
            'url("https://cdn.elearningindustry.com/wp-content/uploads/2016/04/3-functional-lms-wordpress-themes-to-take-your-language-school-to-the-next-level.jpg")',
        ],

        backgroundIndex: 0,
        backgroundAtual: ""
        }
    },

    mounted() {
        this.backgroundAtual = this.backgrounds[this.backgroundIndex];
        this.trocaBackground();
    },

    methods: {
        trocaBackground() {
            setInterval(() => {
                this.backgroundIndex = (this.backgroundIndex + 1) % this.backgrounds.length;
                this.backgroundAtual = this.backgrounds[this.backgroundIndex];
            }, 3000)
        },
    }
}
</script>

<style scoped>
.home {
  height: 700px;
  background-size: cover;
  background-position: center;
  background-position: center;
  transition: background-image 1s ease-in-out;
  overflow-x: hidden;
}
</style>