<template>
    <footer class="rodape container-fluid pt-5 pb-3">
        <h2 class="titulo-2 text-center">Formas de Pagamento</h2>
        <div class="d-flex justify-content-center">
            <div v-for="pagamento in pagamentos" :key="pagamento.id">    
                <i :class="pagamento.icon" class="pagamento-icone my-5 mx-5"></i>
            </div>
        </div>
            <div class="row mt-5">
                <div class="contatos col-12 col-md-6 d-flex flex-column align-items-center">
                    <h2 class="subtitulo">Contatos</h2>
                    <div v-for="contato in contatos" :key="contato.id" class="mt-2">
                        <p class="contato my-3"><i :class="contato.icon" class="contato-icon me-3"></i>{{ contato.descricao }}</p>
                    </div>
                </div>
                <div class="redes-sociais col-12 col-md-6 d-flex flex-column align-items-center mt-4 mt-md-0">
                    <h2 class="subtitulo">Redes Sociais</h2>
                    <div v-for="redeSocial in redesSociais" :key="redeSocial.id" class="mt-2">
                        <a :href="redeSocial.link" target="_blank"><p class="rede-social my-3"><i :class="redeSocial.icon" class="rede-social-icon me-3"></i>{{ redeSocial.descricao }}</p></a>
                    </div>
                </div>
            </div>
    </footer>
    <div class="copyright container-fluid d-flex justify-content-center align-items-center">
         <p>&copy; {{ anoAtual }} FalaFácil. Todos os direitos reservados. Desenvolvido por <a :href="linkedinLeandro" target="_blank"><span class="leandro">Leandro Gonçalves Crisóstomo</span></a></p>
    </div>
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
            ],

            contatos: [
                {
                    id: 1,
                    tipo: "Telefone",
                    icon: "fa-solid fa-phone",
                    descricao: "+55 99 99999-9999"
                },
                {
                    id: 2,
                    tipo: "Email",
                    icon: "fa-solid fa-envelope",
                    descricao: "falafacil@gmail.com"
                },
                {
                    id: 3,
                    tipo: "Atendimento",
                    icon: "fa-solid fa-clock",
                    descricao: "Das 08:00 as 20:00"
                }
            ],

            redesSociais: [
                {
                    id: 1,
                    redeSocial: "Whatsapp",
                    icon: "fa-brands fa-whatsapp",
                    descricao: "+55 99 9999-9999",
                    link: "https://www.whatsapp.com/"
                },
                {
                    id: 2,
                    redeSocial: "Instagram",
                    icon: "fa-brands fa-instagram",
                    descricao: "@falafacil",
                    link: "https://www.instagram.com/"
                },
                {
                    id: 3,
                    redeSocial: "Facebook",
                    icon: "fa-brands fa-facebook",
                    descricao: "@falafacil",
                    link: "https://www.facebook.com/"
                }
            ],

            anoAtual: new Date().getFullYear(),
            linkedinLeandro: "https://www.linkedin.com/in/leandro-gon%C3%A7alves-cris%C3%B3stomo-9936422b0/"
        }
    }
}
</script>

<style scoped>
* {
    color: white;
    margin: 0;
    padding: 0;
    overflow-x: hidden;
    overflow-y: hidden;
}

.rodape {
    background-color: var(--azul-escuro);
}

.pagamento-icone {
    font-size: 2.8em;
    color: var(--vermelho);
}

.subtitulo {
    color: var(--azul-claro);
    font-size: 2.5em;
    text-transform: uppercase;
}

.contato, .rede-social {
    font-size: 1.4em;
}

.contato:hover, .rede-social:hover {
    color: var(--vermelho);
}

.contato-icon, .rede-social-icon {
    color: var(--vermelho);
}

.contato-icon {
    font-size: 1.3em;
}

.rede-social-icon {
    font-size: 1.3em;
}

a {
    text-decoration: none;
}

a:hover {
    color: var(--vermelho);
}

.copyright {
    background-color: #000055;
    text-align: center;
    font-size: 1.1em;
    font-weight: 500;
    letter-spacing: 1px;
    padding-top: 15px;
}

.leandro {
    font-weight: 600;
}

.leandro:hover {
    color: var(--vermelho);
}

@media (min-width: 768px) {
    .copyright {
        font-size: 1.2em;
    }
}
</style>