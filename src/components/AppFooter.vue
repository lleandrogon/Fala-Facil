<template>
    <footer class="rodape container-fluid py-5">
        <h2 class="titulo-2 text-center">Formas de Pagamento</h2>
        <div class="d-flex justify-content-center">
            <div v-for="pagamento in pagamentos" :key="pagamento.id">    
                <i :class="pagamento.icon" class="pagamento-icone my-5 mx-5"></i>
            </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: "AppFooter",

    data() {
        return {
            pagamentos: [
                {
                    id: 1,
                    forma: "Dinheiro",
                    icon: "fa-solid fa-money-bill"
                },
                {
                    id: 2,
                    forma: "Pix",
                    icon: "fa-brands fa-pix"
                },
                {
                    id: 3,
                    forma: "Cartão",
                    icon: "fa-solid fa-credit-card"
                }
            ]
        }
    }
}
</script>

<style scoped>
* {
    color: white;
}

.rodape {
    background-color: var(--azul-escuro);
}

.pagamento-icone {
    font-size: 2.8em;
}
</style>