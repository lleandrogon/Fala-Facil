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
            'url("https://wallpapers.com/images/hd/spanish-background-9nuot4rql38etn3h.jpg")',
            'url("https://csslaval.gouv.qc.ca/wp-content/uploads/2023/05/shutterstock_1274255737_crop-1.jpg")',
            'url("https://st3.depositphotos.com/1022214/15596/i/450/depositphotos_155963228-stock-photo-question-do-you-want-to.jpg")',
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
            }, 2000)
        },
    }
}
</script>

<style>
.home {
  height: 700px;
  background-size: cover;
  background-position: center;
  background-position: center;
  transition: background-image 1s ease-in-out;
}
</style>