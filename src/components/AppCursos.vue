<template>
  <div class="container-fluid cursos py-5">
    <h1 class="titulo text-center">Nossos Cursos</h1>
    <div class="row justify-content-center mt-5 mx-5">
      <div
        v-for="curso in cursos"
        :key="curso.id"
        class="col-md-6 col-lg-4 col-xxl-3 d-flex justify-content-center mb-3 mb-md-5"
      >
        <div class="container-card">
          <div class="container-bandeira">
            <img :src="curso.bandeira" alt="bandeira" class="bandeira">
          </div>
          <div>
            <img :src="curso.imagem" alt="" class="foto">
          </div>
          <div class="conteudo mx-3">
            <h3 class="card-title">{{ curso.nome }}</h3>
            <p class="card-text">{{ curso.descricao }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AppCursos",
  data() {
    return {
      cursos: [
        {
          id: 1,
          nome: "Inglês",
          imagem: "https://viagemeturismo.abril.com.br/wp-content/uploads/2022/10/pedestrians-ga68da657f_1920.jpg?quality=70&strip=info&w=1024",
          bandeira:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f5/Flag_of_the_United_States_%281912-1959%29.svg/2560px-Flag_of_the_United_States_%281912-1959%29.svg.png",
          descricao:
            "Aprenda o idioma mais falado no mundo e expanda suas oportunidades. Curso voltado para iniciantes e avançados.",
        },
        {
          id: 2,
          nome: "Espanhol",
          imagem: "https://images.travelclass.tur.br/upload/2017/04/a-bela-plaza-de-espana-sevilha-espanha-1-1275x850.webp",
          bandeira:
            "https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/Flag_of_Spain.svg/800px-Flag_of_Spain.svg.png",
          descricao:
            "Domine o segundo idioma mais falado do mundo e descubra novas culturas e possibilidades em países de todas as américas e Europa.",
        },
        {
          id: 3,
          nome: "Francês",
          imagem: "https://static.mundoeducacao.uol.com.br/mundoeducacao/2020/11/torre-eiffel.jpg",
          bandeira:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSvim687xZROokAS1hb5uAy9maL7_DVkvGLXg&s",
          descricao:
            "Descubra a língua do amor e da cultura. Ideal para viagens, negócios internacionais ou estudo em universidades francesas e africanas.",
        },
        {
          id: 4,
          nome: "Italiano",
          imagem: "https://viagemeturismo.abril.com.br/wp-content/uploads/2016/10/177493849.jpeg?quality=70&strip=info&w=925&w=636",
          bandeira:
            "https://png.pngtree.com/thumb_back/fw800/background/20220906/pngtree-italian-flag-italia-tricolore-italian-flag-photo-image_9256266.jpg",
          descricao:
            "Explore a língua da arte, da culinária e da moda. Perfeito para conhecer a cultura italiana e se apaixonar por um idioma encantador.",
        },
        {
          id: 5,
          nome: "Alemão",
          imagem: "https://ttoperadora.com.br/wp-content/uploads/2021/01/Alemanha-para-iniciantes-5.jpg",
          bandeira:
            "https://media.istockphoto.com/id/166012239/pt/vetorial/bandeira-da-alemanha.jpg?s=612x612&w=0&k=20&c=6kjExUtW1WlCaAKz1-DuVGAMwGBsGIP3DsaxyMNcD_4=",
          descricao:
            "Desvende o idioma da inovação e da cultura. Aprenda Alemão para explorar oportunidades acadêmicas, profissionais e pessoais.",
        },
        {
          id: 6,
          nome: "Japonês",
          imagem: "https://manualdohomemmoderno.com.br/files/2020/06/japao-pretente-pagar-para-turistas-visitarem-o-pais-depois-da-pandemia-japao-pretente-pagar-para-turistas-visitarem-o-pais-depois-da-pandemia.jpg",
          bandeira:
            "https://s4.static.brasilescola.uol.com.br/be/2022/11/bandeira-do-japao.jpg",
          descricao:
            "Mergulhe na cultura japonesa. Ideal para quem deseja explorar o Japão, a tecnologia e a cultura, como o anime, a culinária e a arte.",
        },
        {
          id: 7,
          nome: "Chinês",
          imagem: "https://www.clubedechines.com.br/wp-content/uploads/2024/05/templo-sanfeng.jpg",
          bandeira:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Flag_of_the_People%27s_Republic_of_China.svg/1200px-Flag_of_the_People%27s_Republic_of_China.svg.png",
          descricao:
            "Desvende o idioma mais falado do mundo e aproxime-se de uma das culturas mais antigas. Perfeito para negócios, viagens e explorar o mercado da China.",
        },
        {
          id: 8,
          nome: "Árabe",
          imagem: "https://guiadoqatar.com.br/wp-content/uploads/2021/06/doha.jpg",
          bandeira:
            "https://mundoeducacao.uol.com.br/upload/conteudo/arabia%20saudita.jpg",
          descricao:
            "Explore o idioma de uma das culturas mais ricas e influentes. Aprenda Árabe para expandir suas oportunidades no mercado global e viajar por países fascinantes.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.cursos {
  background-color: rgb(255, 255, 255);
}

.titulo {
  font-weight: bold;
  font-size: 2.5rem;
}

.container-card {
  width: 330px;
  height: 630px;
  border: none;
  border-radius: 24px;
  background-color: var(--azul-escuro);
  color: var(--azul-claro);
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.container-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 8px 30px rgba(0, 0, 0, 0.3);
  background-color: var(--azul-claro);
  color: var(--azul-escuro);
}

.container-bandeira {
  position: absolute;
  top: 275px;
  left: 50%;
  transform: translate(-50%, -50%);
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  border-radius: 50%;
}

.bandeira {
  width: 60px;
  height: 60px;
  border: none;
  border-radius: 50%;
}

.foto {
  width: 100%;
  height: 275px;
  border-radius: 24px 24px 0 0;
}

.conteudo {
  text-align: center;
}

.card-title {
  font-size: 1.8rem;
  font-weight: 600;
  margin: 30px 0 20px 0;
}

.card-text {
  font-size: 1.1em;
  font-weight: 500;
  letter-spacing: 1px;
  line-height: 1.6;
}

@media (min-width: 768px) {
  .container-card {
    height: 550px;
  }
}
</style>