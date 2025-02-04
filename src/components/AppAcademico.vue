<template>
  <section class="academico py-5">
    <div class="text-center">
      <h1 class="titulo-2">Excelência Acadêmica</h1>
      <p class="subtitulo">
        Os objetivos do mundo contemporâneo e nossa jornada rumo à excelência
        acadêmica, guiados por uma proposta estruturada nos seguintes pilares:
      </p>
      <div class="d-flex justify-content-center align-items-center mt-5">
        <div v-for="academico in academicos" :key="academico.id">
          <div class="card mx-3">
            <img :src="academico.imagem" class="card-img-top" alt="imagem" />
            <div class="card-body">
              <h5 class="card-title mt-3">{{ academico.titulo }}</h5>
              <p class="card-text mt-2">
                Some quick example text to build on the card title and make up
                the bulk of the card's content.
              </p>
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
          imagem: "https://img.freepik.com/fotos-premium/um-grupo-diversificado-de-jovens-individuos-envolvidos-em-uma-conversa-enquanto-sentados-em-uma-mesa-grupo-de-alunos-falando-e-escrevendo-na-escola-ai-gerado_538213-36699.jpg",
          titulo: "Conversas em grupo",
          descricao: "lorem ipsum dolor",
        },
        {
          id: 2,
          imagem: "https://www.conteudoinboundmarketing.com.br/wp-content/uploads/2018/06/criatividade-executivo.jpg",
          titulo: "Criatividade",
          descricao: "",
        },
        {
          id: 3,
          imagem: "https://p2.trrsf.com/image/fget/cf/774/0/images.terra.com/2023/05/05/1843501042-homem-cantando.jpg",
          titulo: "Canto",
          descricao: "",
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
  font-size: 1.2em;
  margin-top: 30px;
}

.card {
    width: 360px;
    height: 550px;
    border: none;
    border-radius: 25px;
}

.card img {
    border-radius: 25px 25px 0 0;
    height: 250px;
}
</style>