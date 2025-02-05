<template>
  <section class="academico py-5 mt-3 mt-md-0">
    <div class="text-center">
      <h1 class="titulo-2">Excelência Acadêmica</h1>
      <p class="subtitulo">
        Os objetivos do mundo contemporâneo e nossa jornada rumo à excelência
        acadêmica, guiados por uma proposta estruturada nos seguintes pilares:
      </p>
      <div class="row mt-5">
        <div
          v-for="academico in academicos"
          :key="academico.id"
          class="col-md-4 col-lg-3 d-flex justify-content-center my-3 my-md-0"
        >
          <div class="card">
            <img :src="academico.imagem" class="card-img-top" alt="imagem" />
            <div class="card-body">
              <h5 class="titulo-card">{{ academico.titulo }}</h5>
              <p class="descricao mt-2">{{ academico.descricao }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppAcademico",

  data() {
    return {
      academicos: [
        {
          id: 1,
          imagem:
            "https://img.freepik.com/fotos-premium/um-grupo-diversificado-de-jovens-individuos-envolvidos-em-uma-conversa-enquanto-sentados-em-uma-mesa-grupo-de-alunos-falando-e-escrevendo-na-escola-ai-gerado_538213-36699.jpg",
          titulo: "Conversas em grupo",
          descricao:
            "O aprendizado colaborativo permite a troca de ideias e experiências entre os participantes. Essa interação promove não apenas o crescimento intelectual, mas também o desenvolvimento de habilidades sociais essenciais para a vida acadêmica e profissional.",
        },
        {
          id: 2,
          imagem:
            "https://www.conteudoinboundmarketing.com.br/wp-content/uploads/2018/06/criatividade-executivo.jpg",
          titulo: "Criatividade",
          descricao:
            "A criatividade é uma ferramenta fundamental para a inovação e a resolução de problemas. Estimulá-la permite que os alunos pensem de maneira original e encontrem soluções inovadoras para os desafios do dia a dia.",
        },
        {
          id: 3,
          imagem:
            "https://p2.trrsf.com/image/fget/cf/774/0/images.terra.com/2023/05/05/1843501042-homem-cantando.jpg",
          titulo: "Canto",
          descricao:
            "A música é uma poderosa forma de expressão e desenvolvimento pessoal. Cantar melhora a autoconfiança, a comunicação e contribui para o bem-estar emocional, além de estimular a memória e a concentração.",
        },
        {
          id: 4,
          imagem:
            "https://blog.tris.com.br/wp-content/uploads/2023/07/menina-fazendo-apresentacao-em-sala-de-aula-para-professora-e-colegas.jpeg",
          titulo: "Metacognição",
          descricao:
            "A metacognição é a capacidade de entender e regular o próprio aprendizado. Desenvolver essa habilidade permite que os alunos aprimorem suas estratégias de estudo e alcancem um desempenho acadêmico mais eficiente e consciente.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.academico {
  background-color: var(--azul-escuro);
  color: white;
}

.subtitulo {
  font-size: 1.1em;
  margin-top: 30px;
  opacity: 0.9;
}

.row {
  margin-right: 0;
  margin-left: 0;
}

.card {
  width: 360px;
  height: 580px;
  border: none;
  border-radius: 25px;
  box-shadow: 0px 4px 10px var(--azul);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0px 6px 15px var(--azul-claro);
}

.card img {
  border-radius: 25px 25px 0 0;
  height: 260px;
  border-bottom: 3px solid var(--vermelho);
}

.titulo-card {
  font-size: 1.7em;
  font-weight: 900;
  color: var(--vermelho);
  text-transform: uppercase;
  margin: 15px 0;
  font-weight: 600;
}

.descricao {
  font-size: 1.1em;
  opacity: 0.8;
  text-align: center;
}

@media (min-width: 768px) {
  .subtitulo {
    font-size: 1.2em;
  }
}
</style>