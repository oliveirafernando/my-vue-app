<template>
  <div>
    <div class="jumbotron">
      <div class="container">
        <h1 class="display-4">Calculadora de IMC</h1>
        <p class="lead">
          Esta página é uma exemplo de calculadora de IMC usando programação
          reativa com Vue.
        </p>
      </div>
    </div>

    <div class="container">
      <form @submit="cadastrarPessoa($form)">
        <div class="form-group row">
          <label for="nomeInputLabel" class="col-sm-2 col-form-label">
            Nome
          </label>
          <div class="col-sm-10">
            <input
              autofocus
              type="text"
              class="form-control"
              id="nomeInputLabel"
            />
          </div>
        </div>

        <div class="form-group row">
          <label for="pesoInputLabel" class="col-sm-2 col-form-label">
            Peso
          </label>
          <div class="col-sm-10">
            <input type="text" class="form-control" id="pesoInputLabel" />
          </div>
        </div>

        <div class="form-group row">
          <label for="alturaInputLabel" class="col-sm-2 col-form-label">
            Altura
          </label>
          <div class="col-sm-10">
            <input type="text" class="form-control" id="alturaInputLabel" />
          </div>
        </div>

        <div class="form-group row">
          <label class="col-sm-2 col-form-label"></label>
          <div class="col-sm-10">
            <button class="btn btn-primary mb-4" type="submit">Calcular</button>
          </div>
        </div>
      </form>

      <div class="row">
        <table class="table table-striped">
          <thead>
            <tr>
              <th scope="col">Nome</th>
              <th scope="col">Peso</th>
              <th scope="col">Altura</th>
              <th scope="col">IMC</th>
            </tr>
          </thead>

          <tbody v-for="pessoa in pessoas">
            <tr>
              <td itemScope="row">{{ pessoa.nome }}</td>
              <td itemScope="row">{{ pessoa.peso }}</td>
              <td itemScope="row">{{ pessoa.altura }}</td>
              <td itemScope="row">{{ pessoa.imc }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Imc",
  data() {
    return {
      pessoas: [
        {
          nome: "Fernando",
          peso: 82,
          altura: 180,
          imc: 82 / (180 * 180),
        },
      ],
    };
  },

  methods: {
    cadastrarPessoa: function (form) {
      //todo;
      this.pessoas.push({
        nome: "Mateus",
        peso: 81,
        altura: 181,
        imc: 81 / (181 * 181),
      });
      console.log(">>> Submit: " + form);
    },
  },
};
</script>
