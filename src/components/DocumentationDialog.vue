<template>
  <q-dialog ref="dialog">
    <div class="col-12 col-md-12" style="width: 60% !important;">
      <q-card>
        <q-card-section class="bg-white">
          <div class="row justify-between">
            <div class="text-h3 text-bold text-primary q-pa-md">
              Documentação CalcFácil
            </div>
            <q-btn v-close-popup flat icon="close" />
          </div>

          <q-separator />
          <br />

          <div class="q-px-md q-py-sm">
            <span class="text-h4 text-bold">Introdução</span>

            <p class="q-pt-sm no-margin">Bem-vindo à documentação do projeto CalcFácil! A CalcFácil é uma calculadora
              virtual que oferece uma gama de funcionalidades matemáticas para atender às suas necessidades de cálculo.
              Este documento fornecerá informações detalhadas sobre como usar o CalcFácil e suas principais
              características.</p>
          </div>

          <div class="q-px-md q-py-sm">
            <span class="text-h4 text-bold">Iniciando a CalcFácil</span>
            <br /><br />

            <span class="text-h5 text-bold q-px-md">1. Interface do Usuário</span>
            <p class="q-py-sm q-px-lg no-margin">A interface da CalcFácil é projetada para ser intuitiva e fácil de usar.
              Ela consiste em uma área de entrada de cálculo na parte superior e diversos botões com retornos e
              funcionalidades individuais.</p><br />

            <span class="text-h5 text-bold q-px-md">2. Legenda dos botões</span>
            <div class="q-py-sm q-px-lg q-gutter-xs">
              <div class="row items-center">
                <div>
                  <q-btn size="xs" color="red-9" class="q-mr-md" />
                </div>
                <span class="subtitle_text">Limpeza e Correção de Entradas</span>
              </div>

              <div class="row items-center">
                <div>
                  <q-btn size="xs" color="grey-9" class="q-mr-md" />
                </div>
                <span class="subtitle_text">Teclado Numérico</span>
              </div>

              <div class="row items-center">
                <div>
                  <q-btn size="xs" color="orange-8" class="q-mr-md" />
                </div>
                <span class="subtitle_text">Operadores Básicas</span>
              </div>

              <div class="row items-center">
                <div>
                  <q-btn size="xs" color="grey-8" class="q-mr-md" />
                </div>
                <span class="subtitle_text">Operadores Avançadas</span>
              </div>

              <div class="row items-center">
                <div>
                  <q-btn size="xs" color="blue-10" class="q-mr-md" />
                </div>
                <span class="subtitle_text">Resultado da Operação</span>
              </div>
            </div>
          </div>

          <div class="q-px-md q-py-sm">
            <span class="text-h4 text-bold">Como Usar?</span>
            <br /><br />

            <span class="text-h5 text-bold q-px-md">1. Operação Básica</span>
            <p class="q-py-sm q-px-lg no-margin">Para realizar cálculos de operação básica, use o teclado númerico para
              inserir os números desejados, selecione o operador escolhido e clicar no botão '=' para obter o resultado
              da operação.</p>
            <div class="row col-12 q-px-md q-pb-sm">
              <q-img src="../assets/Documentation/operacao1.png" class="col-md-3 img" />
              <q-img src="../assets/Documentation/operacao2.png" class="col-md-3 img" />
              <q-img src="../assets/Documentation/operacao3.png" class="col-md-3 img" />
              <q-img src="../assets/Documentation/operacao4.png" class="col-md-3 img" />
            </div><br />

            <span class="text-h5 text-bold q-px-md">2. Limpeza e Correção de Entradas</span>
            <p class="q-py-sm q-px-lg no-margin">Se um erro for cometido ao inserir números ou operadores, o botão de
              correção de entrada ("BACKSPACE") permite que os usuários apaguem o último caractere, já o botão de limpeza
              ("CLEAN") permite que os usuários apaguem a entrada inteira antes de inserir
              novamente.</p><br />

            <span class="text-h5 text-bold q-px-md">3. Potenciação</span>
            <p class="q-py-sm q-px-lg no-margin">Para realizar cálculos com potenciação, use o teclado númerico para
              inserir os números desejados, selecione o operador de potenciação representado por "xⁿ" e clicar no botão
              '=' para obter o resultado da operação.</p>
            <div class="row col-12 q-px-md q-pb-sm">
              <q-img src="../assets/Documentation/potencia1.png" class="col-md-3 img" />
              <q-img src="../assets/Documentation/potencia2.png" class="col-md-3 img" />
              <q-img src="../assets/Documentation/potencia3.png" class="col-md-3 img" />
              <q-img src="../assets/Documentation/potencia4.png" class="col-md-3 img" />
            </div>
          </div>

          <div class="q-px-md q-py-sm">
            <span class="text-h4 text-bold">Suporte e Contato</span>
            <br /><br />

            <span class="text-h5 text-bold q-px-md">1. Suporte Técnico</span>
            <p class="q-py-sm q-px-lg no-margin">Para obter suporte técnico ou relatar problemas, entre em contato conosco
              através do e-mail de suporte: <a href="mailto:suporte@calcfacil.com">suporte@calcfacil.com</a></p><br />

            <span class="text-h5 text-bold q-px-md">2. Feedback do Usuário</span>
            <p class="q-py-sm q-px-lg no-margin">Valorizamos o seu feedback! Se você tiver sugestões ou comentários sobre
              o CalcFácil, por favor, nos informe através do nosso formulário de feedback em nosso site oficial.</p><br />
          </div>
        </q-card-section>
      </q-card>
    </div>
  </q-dialog>
</template>
<script>
export default {
  name: 'DocumentationDialog'
}
</script>
<style>
p,
.subtitle_text {
  font-size: 16px;
}

.img {
  border: 2px solid black;
}
</style>
