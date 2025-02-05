<template>
  <section class="perguntas container-fluid d-flex flex-column align-items-center">
    <h1 class="titulo text-center">Perguntas Frequentes</h1>
    <div v-for="pergunta in perguntas" :key="pergunta.id" class="mt-4 w-75">
      <div class="pergunta-container d-flex justify-content-between align-items-center" @click="mostrarResposta(pergunta.id)">
        <span class="pergunta-texto">{{ pergunta.pergunta }}</span>
        <i 
          class="mais fa-solid" 
          :class="{ 'fa-plus': !respostas[pergunta.id], 'fa-minus': respostas[pergunta.id], 'rotacao': respostas[pergunta.id] }"
        ></i>
      </div>
      <transition name="deslizar">
        <div v-if="respostas[pergunta.id]" class="resposta">
          <p>{{ pergunta.resposta }}</p>
        </div>
      </transition>
    </div>
  </section>
</template>

<script>
export default {
  name: "AppPerguntas",

  data() {
    return {
      perguntas: [
        { id: 1, pergunta: "A Fala-Fácil tem cursos online?", resposta: "Sim, temos cursos online, basta entrar em contato conosco para saber mais sobre o melhor ensino para você." },
        { id: 2, pergunta: "Qual a duração dos cursos?", resposta: "Os cursos são divididos em módulos, cada módulo é concluído em 1 ano, totalizando 3 anos de curso." },
        { id: 3, pergunta: "Os cursos possuem certificado?", resposta: "Sim! Todos os nossos cursos oferecem certificados reconhecidos para comprovar sua qualificação." },
        { id: 4, pergunta: "Preciso ter conhecimento prévio para fazer um curso?", resposta: "Não. Nossos cursos são estruturados para atender tanto iniciantes quanto alunos com experiência prévia." },
        { id: 5, pergunta: "Quais são as formas de pagamento disponíveis?", resposta: "Aceitamos pagamentos via cartão de crédito, boleto bancário e transferência bancária." },
        { id: 6, pergunta: "Os cursos têm suporte ao aluno?", resposta: "Sim! Nossos alunos têm acesso a suporte pedagógico e tutores especializados para tirar dúvidas." },
        { id: 7, pergunta: "Posso acessar as aulas a qualquer momento?", resposta: "Sim! Nossos cursos online são gravados e você pode acessá-los no horário que for mais conveniente para você." },
        { id: 8, pergunta: "Vocês oferecem aulas presenciais?", resposta: "Sim, temos unidades físicas onde oferecemos aulas presenciais. Entre em contato para saber mais!" }
      ],
      respostas: {}
    };
  },

  methods: {
    mostrarResposta(id) {
      this.respostas[id] = !this.respostas[id];
    }
  }
};
</script>

<style scoped>
.perguntas {
  padding: 80px 0 50px 0;
}

.pergunta-container {
  background-color: rgb(224, 224, 224);
  padding: 20px;
  cursor: pointer;
  border-radius: 8px;
  transition: background 0.3s;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
}

.pergunta-container:hover {
  background-color: #d2d2d2;
}

.pergunta-texto {
  font-size: 1.2em;
  font-weight: bold;
  color: #333;
}

.mais {
  color: var(--vermelho);
  font-size: 1.5em;
  transition: transform 0.3s ease;
}

.rotacao {
  transform: rotate(180deg);
}

.deslizar-enter-active, .deslizar-leave-active {
  transition: max-height 0.4s ease-out, opacity 0.4s ease-out;
  overflow: hidden;
}

.deslizar-enter-from, .deslizar-leave-to {
  max-height: 0;
  opacity: 0;
}

.deslizar-enter-to, .deslizar-leave-from {
  max-height: 200px;
  opacity: 1;
}

.resposta {
  background-color: #f8f8f8;
  display: flex;
  align-items: center;
  padding: 5px 15px;
  border-left: 4px solid var(--vermelho);
  border-radius: 5px;
  font-size: 1.1em;
  font-weight: 600;
}

.resposta p {
  margin-top: 15px;
}
</style>