<template>
  <div :style="{ backgroundImage: backgroundAtual }" class="container-fluid home"></div>
</template>

<script>
export default {
    name: "AppHome",

    data() {
        return {
        backgrounds: [
            'url("https://circuitomt.com.br/wp-content/uploads/2024/07/unnamed-34-1254x700.jpg")',
            'url("https://culturainglesacuritiba.com.br/wp-content/uploads/2022/02/iStock-1305349522.jpg")',
            'url("https://blog.portalpos.com.br/wp-content/uploads/2022/07/como-ser-professor-de-ingles.jpg")',
            'url("https://www.britishcouncil.org/sites/default/files/european_day_of_languages_1.png")',
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
  height: 750px;
  background-size: cover;
  background-position: center;
  background-position: center;
  transition: background-image 1s ease-in-out;
  overflow-x: hidden;
}
</style>