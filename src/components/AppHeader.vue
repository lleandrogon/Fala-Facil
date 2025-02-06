<template>
    <div class="container-fluid custom-container">
        <div class="inicio"></div>
        <nav class="row">
            <div class="col-6 d-flex align-items-center">
                <img :src="logo" alt="Logo" class="logo img-fluid ms-3">
            </div>
            <div class="col-6 d-flex d-md-none justify-content-end align-items-center">
                <i class="menu-burger fa-solid fa-bars me-3" @click="showNav()"></i>
            </div>
            <div v-if="navResponsivo" class="text-center d-md-none">
                <ul class="lista-responsiva">
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('cursos')">Cursos</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('matricula')">Matricula</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('parceria')">Parceria</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('academico')">Acadêmico</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('perguntas')">Perguntas</a></li>
                </ul>
            </div>
            <div class="col-6 d-none d-md-flex justify-content-end align-items-center mt-4">
                <ul class="lista d-flex">
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('cursos')">Cursos</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('matricula')">Matricula</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('parceria')">Parceria</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('academico')">Acadêmico</a></li>
                    <li class="sem-marcadores"><a href="#" class="sem-sublinhado" @click="rolagem('perguntas')">Perguntas</a></li>
                </ul>
            </div>
        </nav>
    </div>
</template>

<script>
export default {
    name: "AppHeader",

    data() {
        return {
            logo: "logo.png",
            navResponsivo: false
        }
    },

    methods: {
        showNav() {
            this.navResponsivo = !this.navResponsivo;
        },

        rolagem(sessaoId) {
            const sessao = document.getElementById(sessaoId);
            if (sessao) {
                sessao.scrollIntoView({ behavior: 'smooth' });
                this.navResponsivo = false;
            }
        }
    }
}
</script>

<style scoped>
    .custom-container {
        width: 100%;
        padding-left: 0;
        padding-right: 0;
        overflow-x: hidden;
    }

    .inicio {
        height: 30px;
        background-color: var(--azul-escuro);
        width: 100%;
        border-bottom: 3px solid var(--vermelho);
    }

    .logo {
        width: 110px;
    }

    .menu-burger {
        font-size: 50px;
        cursor: pointer;
        transition: transform 0.3s ease;
    }

    .menu-burger:hover {
        color: var(--vermelho);
        transform: rotate(90deg);
    }
    
    .lista-responsiva li {
        padding: 20px 0;
    }

    .lista-responsiva li a {
        font-size: 1.7em;
        color: black;
        text-transform: uppercase;
        transition: 0.3s;
        font-weight: 500;
    }

    .lista-responsiva li a:hover {
        color: var(--vermelho);
    }

    .lista li {
        margin: 0 20px;
    }

    .lista li a {
        font-size: 1.7em;
        color: black;
        transition: 0.3s;
        text-transform: uppercase;
        font-weight: 500;
    }

    .lista li a:hover {
        color: var(--vermelho);
    }

    @media (max-width: 992px) {
        .lista li a {
            font-size: 1.4em;
        }
    }
</style>