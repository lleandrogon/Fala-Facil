<template>
  <section class="matricula container-fluid py-5">
    <h1 class="titulo-2 text-center">Matricule-se</h1>
    <div class="row">
      <div class="col-12 col-md-7">
        <form action="" class="row px-2">
          <div class="mb-3 col-lg-6">
            <label for="nome" class="form-label">Nome Completo</label>
            <input type="text" class="form-control" id="nome" v-model="nome" />
          </div>
          <div class="mb-3 col-lg-6">
            <label for="telefone" class="form-label">Telefone</label>
            <input type="text" class="form-control" id="telefone" v-model="telefone" />
          </div>
          <div class="mb-3 col-lg-6">
            <label for="email" class="form-label">Email</label>
            <input type="email" class="form-control" id="email" v-model="email" />
          </div>
          <div class="mb-3 col-lg-6">
            <label for="estado" class="form-label">Estado</label>
            <select
              name="estado"
              id="estado"
              class="form-control col-lg-6"
              v-model="estado"
              @change="atualizarCidades"
            >
              <option value="AC">Acre</option>
              <option value="AL">Alagoas</option>
              <option value="AP">Amapá</option>
              <option value="AM">Amazonas</option>
              <option value="BA">Bahia</option>
              <option value="CE">Ceará</option>
              <option value="DF">Distrito Federal</option>
              <option value="ES">Espírito Santo</option>
              <option value="GO">Goiás</option>
              <option value="MA">Maranhão</option>
              <option value="MT">Mato Grosso</option>
              <option value="MS">Mato Grosso do Sul</option>
              <option value="MG">Minas Gerais</option>
              <option value="PA">Pará</option>
              <option value="PB">Paraíba</option>
              <option value="PR">Paraná</option>
              <option value="PE">Pernambuco</option>
              <option value="PI">Piauí</option>
              <option value="RJ">Rio de Janeiro</option>
              <option value="RN">Rio Grande do Norte</option>
              <option value="RS">Rio Grande do Sul</option>
              <option value="RO">Rondônia</option>
              <option value="RR">Roraima</option>
              <option value="SC">Santa Catarina</option>
              <option value="SP">São Paulo</option>
              <option value="SE">Sergipe</option>
              <option value="TO">Tocantins</option>
            </select>
          </div>
          <div class="mb-3 col-lg-6">
            <label for="cidade" class="form-label">Cidade</label>
            <select name="cidade" id="cidade" class="form-control col-lg-6" v-model="cidade">
              <option value=""></option>
            </select>
          </div>
          <div class="mb-3 col-lg-6">
            <label for="idioma" class="form-label">Idioma</label>
            <select name="idioma" id="idioma" class="form-control" v-model="idioma">
              <option value="ingles">Inglês</option>
              <option value="espanhol">Espanhol</option>
              <option value="frances">Francês</option>
              <option value="italiano">Italiano</option>
              <option value="alemao">Alemão</option>
              <option value="japones">Japonês</option>
              <option value="chines">Chinês</option>
              <option value="arabe">Árabe</option>
            </select>
          </div>
          <div class="mb-3">
            <label for="nivel" class="form-label">Nível de Fluência</label>
            <select name="nivel" id="nivel" class="form-control" v-model="nivel">
              <option value="iniciante">Iniciante</option>
              <option value="basico">Básico</option>
              <option value="intermediario">Intermediário</option>
              <option value="avancado">Avançado</option>
            </select>
          </div>
          <div class="botoes mt-3">
            <button type="button" @click="enviarFormulario()" class="botao me-2">Enviar</button>
            <button type="button" @click="limparFormulario()" class="botao ms-2">Limpar</button>
          </div>
        </form>
      </div>
      <div class="imagem col-12 col-md-5 d-none d-md-block"></div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      cidadesPorEstado: {
        AC: ["Rio Branco", "Cruzeiro do Sul", "Sena Madureira"],
        AL: ["Maceió", "Arapiraca", "Marechal Deodoro"],
        AP: ["Macapá", "Santana"],
        AM: ["Manaus", "Parintins", "Itacoatiara"],
        BA: ["Salvador", "Feira de Santana", "Vitória da Conquista"],
        CE: ["Fortaleza", "Caucaia", "Juazeiro do Norte"],
        DF: ["Brasília", "Taguatinga", "Ceilândia"],
        ES: ["Vitória", "Vila Velha", "Serra"],
        GO: ["Goiânia", "Aparecida de Goiânia", "Anápolis"],
        MA: ["São Luís", "Imperatriz", "Caxias"],
        MT: ["Cuiabá", "Várzea Grande", "Rondonópolis"],
        MS: ["Campo Grande", "Dourados", "Três Lagoas"],
        MG: ["Belo Horizonte", "Uberlândia", "Contagem"],
        PA: ["Belém", "Ananindeua", "Santarém"],
        PB: ["João Pessoa", "Campina Grande", "Patos"],
        PR: ["Curitiba", "Londrina", "Maringá"],
        PE: ["Recife", "Olinda", "Jaboatão dos Guararapes"],
        PI: ["Teresina", "Parnaíba", "Picos"],
        RJ: ["Rio de Janeiro", "Niterói", "Duque de Caxias"],
        RN: ["Natal", "Mossoró", "Parnamirim"],
        RS: ["Porto Alegre", "Caxias do Sul", "Pelotas"],
        RO: ["Porto Velho", "Ji-Paraná", "Ariquemes"],
        RR: ["Boa Vista", "Rorainópolis"],
        SC: ["Florianópolis", "Joinville", "Blumenau"],
        SP: ["São Paulo", "Campinas", "Santos"],
        SE: ["Aracaju", "Lagarto", "Itabaiana"],
        TO: ["Palmas", "Araguaína", "Gurupi"],
      },

      nome: "",
      telefone: "",
      email: "",
      estado: "",
      cidade: "",
      idioma: "",
      nivel: ""
    };
  },

  methods: {
    atualizarCidades(event) {
      const estadoSelecionado = event.target.value;
      const selectCidade = document.getElementById("cidade");

      selectCidade.innerHTML = '<option value=""></option>';

      if (this.cidadesPorEstado[estadoSelecionado]) {
        this.cidadesPorEstado[estadoSelecionado].forEach((cidade) => {
          const option = document.createElement("option");
          option.value = cidade;
          option.textContent = cidade;
          selectCidade.appendChild(option);
        });
      }
    },

    enviarFormulario() {
        if (this.validaFormulario()) {
            const mensagem = `Olá! Gostaria de me matricular no curso. Aqui estão meus dados:\n\nNome: ${this.nome}\nTelefone: ${this.telefone}\nEmail: ${this.email}\nEstado: ${this.estado}\nCidade: ${this.cidade}\nIdioma: ${this.idioma}\nNível de Fluência: ${this.nivel}`;

            const numero = "5599999999999";
            const urlWhatsApp = `https://wa.me/${numero}?text=${encodeURIComponent(mensagem)}`;

            window.open(urlWhatsApp, '_blank');

            this.limparFormulario();
        } else {
            alert("Por favor, preencha todos os campos corretamente.");
        }
    },

    limparFormulario() {
      this.nome = "";
      this.telefone = "";
      this.email = "";
      this.estado = "";
      this.cidade = "";
      this.idioma = "";
      this.nivel = "";
      this.atualizarCidades({ target: { value: "" } });
    },

    validaFormulario() {
        return this.nome !== "" && this.telefone !== "" && this.email !== "" && this.estado !== "" && this.cidade !== "" && this.idioma !== "" && this.nivel !== "";
    }
  },
};
</script>

<style scoped>
.matricula {
  background-color: var(--azul-escuro);
  color: white;
}

.titulo-2 {
  margin-bottom: 80px;
}

.imagem {
  background: url("https://png.pngtree.com/png-vector/20220526/ourmid/pngtree-online-language-school-flat-design-concept-with-woman-on-smartphone-screen-png-image_4724410.png");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}
</style>