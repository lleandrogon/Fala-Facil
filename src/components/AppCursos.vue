<template>
  <div class="container-fluid cursos my-5">
    <h1 class="titulo text-center">Nossos Cursos</h1>
    <div class="row d-flex justify-content-center align-items-center mt-5">
      <div
        v-for="curso in cursos"
        :key="curso.id"
        class="col-md-2 d-flex justify-content-center my-2 my-md-0"
      >
        <div class="card" style="width: 16rem">
          <img :src="curso.bandeira" class="card-img-top mx-auto" alt="Bandeira" />
          <div class="card-body text-center">
            <h3 class="mb-3">{{ curso.nome }}</h3>
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
          bandeira:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/f/f5/Flag_of_the_United_States_%281912-1959%29.svg/2560px-Flag_of_the_United_States_%281912-1959%29.svg.png",
          descricao:
            "Aprenda o idioma mais falado no mundo e expanda suas oportunidades. Curso voltado para iniciantes e avançados.",
        },
        {
          id: 2,
          nome: "Espanhol",
          bandeira:
            "https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/Flag_of_Spain.svg/800px-Flag_of_Spain.svg.png",
          descricao:
            "Domine o segundo idioma mais falado do mundo e descubra novas culturas e possibilidades em países de todas as américas e Europa.",
        },
        {
          id: 3,
          nome: "Francês",
          bandeira:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSvim687xZROokAS1hb5uAy9maL7_DVkvGLXg&s",
          descricao:
            "Descubra a língua do amor e da cultura. Ideal para viagens, negócios internacionais ou estudo em universidades francesas e africanas.",
        },
        {
          id: 4,
          nome: "Italiano",
          bandeira:
            "https://png.pngtree.com/thumb_back/fw800/background/20220906/pngtree-italian-flag-italia-tricolore-italian-flag-photo-image_9256266.jpg",
          descricao:
            "Explore a língua da arte, da culinária e da moda. Perfeito para conhecer a cultura italiana e se apaixonar por um idioma encantador.",
        },
        {
            id: 5,
            nome: "Alemão",
            bandeira: "https://media.istockphoto.com/id/166012239/pt/vetorial/bandeira-da-alemanha.jpg?s=612x612&w=0&k=20&c=6kjExUtW1WlCaAKz1-DuVGAMwGBsGIP3DsaxyMNcD_4=",
            descricao: "Desvende o idioma da inovação e da cultura. Aprenda Alemão para explorar oportunidades acadêmicas, profissionais e pessoais."
        },
        {
            id: 6,
            nome: "Japonês",
            bandeira: "https://s4.static.brasilescola.uol.com.br/be/2022/11/bandeira-do-japao.jpg",
            descricao: "Mergulhe na cultura japonesa. Ideal para quem deseja explorar o Japão, a tecnologia e a cultura, como o anime, a culinária e a arte."
        },
      ],
    };
  },
};
</script>

<style scoped>
.card {
  background-color: var(--azul);
  color: white;
  border: none;
  border-radius: 30px;
  transition: transform 0.3s, box-shadow 0.3s;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
}

.card img {
  height: 200px;
  width: 200px;
  padding: 20px;
  border-radius: 50%;
  object-fit: cover;
}

h3 {
    font-size: 2em;
}

.card-text {
  font-size: 1.2em;
  font-weight: 500;
}
</style>