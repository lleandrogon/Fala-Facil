<template>
    <section class="parceria container-fluid pt-5">
        <div class="row pt-5">
            <div class="imagem col-xl-4 d-none d-xl-block">
                
            </div>
            <div class="col-xl-8 text-center mb-xl-5">
                <h2 class="titulo">Parceria Internacional</h2>
                <div class="college mt-4">
                    <h3>Florida<span>College</span></h3>
                </div>
                <p class="descricao mt-5 mx-2">Nós da Fala Fácil preparamos você para poder estudar em umas das melhores universidades dos Estados Unidos <strong>totalmente de graça</strong>.</p>
                <div class="beneficios-container row mt-4 mx-2">
                    <div v-for="beneficio in beneficios" :key="beneficio.id" class="beneficios col-lg-6">
                        <i :class="beneficio.icon" class="me-2"></i>
                        <span class="ms-1 ms-md-4">{{ beneficio.descricao }}</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "AppParceria",

    data() {
        return {
            beneficios: [
                {
                    id: 1,
                    icon: "fa-solid fa-book",
                    descricao: "Acesso a materiais exclusivos pra estudo."
                },
                {
                    id: 2,
                    icon: "fa-solid fa-chalkboard-user",
                    descricao: "Mentoria com professores internacionais."
                },
                {
                    id: 3,
                    icon: "fa-solid fa-bag-shopping",
                    descricao: "Suporte completo para bolsas de estudo."
                },
                {
                    id: 4,
                    icon: "fa-solid fa-certificate",
                    descricao: "Certificados reconhecidos mundialmente."
                }
            ]
        }
    }
}
</script>

<style scoped>
.imagem {
    background: url("https://rosepng.com/wp-content/uploads/2024/07/s11728_indian_student_isolated_on_white_background_a74ccb1c-8b7a-48cd-b640-fe7ac5838d68_2-photoroom.png");
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}

.titulo {
    color: var(--vermelho);
    font-family: "Poppins", sans-serif;
    font-size: 3.5em;
    font-weight: bold;
    margin-bottom: 1rem;
    text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.3);
}

.college {
    display: inline-block;
    background: linear-gradient(135deg, var(--azul-escuro), rgb(0, 119, 255));
    color: white;
    font-family: "Poppins", cursive;
    padding: 15px 30px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.college:hover {
    transform: scale(1.05);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
}

.college h3 {
    font-size: 2.8em;
    margin: 0;
}

.college span {
    color: var(--azul-bebe);
    font-weight: bold;
}

.descricao {
    font-size: 1.4em;
    font-family: "Poppins", sans-serif;
    line-height: 1.8;
    font-weight: 500;
    text-align: justify;
}

.descricao span {
    color: var(--vermelho);
    font-weight: bold;
}

.descricao strong {
    color: var(--azul-escuro);
    font-weight: bold;
}

.beneficios-container {
    background-color: var(--azul-escuro);
    border: none;
    border-radius: 15px;
    padding: 0 10px;
    color: white;
}

.beneficios {
    font-size: 1.5em;
    margin: 25px 0;
}

.beneficios i {
    color: var(--azul-bebe);
}

@media (max-width: 768px) {
    .imagem {
        height: 200px;
    }

    .titulo {
        font-size: 2.5em;
    }

    .college h3 {
        font-size: 2em;
    }

    .descricao {
        font-size: 1.2em;
    }
}
</style>