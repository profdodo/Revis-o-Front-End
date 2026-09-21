1-O que são variáveis ​​CSS e quando você as usaria?
São valores customizados definidos com --nome: valor e usados com var(--nome).
Uso: quando você repete cores, espaçamentos, fontes. Facilita tema claro/escuro, manutenção e troca de valores em tempo real via JS.css:root { --cor-primaria: #6c5ce7; }
.botao { background: var(--cor-primaria); }
2-Como funciona o loop de eventos em JavaScript?
JS é single-thread. O Event Loop é o que permite ser assíncrono.Call Stack: onde o código é executado.Web APIs: onde ficam setTimeout, fetch, eventos do DOM.Callback Queue / Microtask Queue: onde as callbacks esperam.
O Loop fica verificando: se o Stack está vazio, pega o que está na Microtask Queue (Promises tem prioridade) e depois na Callback Queue e joga pro Stack executar.
3-Quais são as diferentes maneiras de lidar com operações assíncronas em JavaScript?
Callbacks: fs.readFile(..., callback) - gera Callback Hell.Promises: .then().catch() - encadeamento melhor.Async/Await: açúcar sintático em cima de Promise, código parece síncrono. É o padrão hoje.
4-Como gerenciar o estado em aplicações de página única?
Local: useState / data() dentro do componente.
Global Simples: Context API, Pinia/Vuex, Zustand.
Global Complexo: Redux, com reducers e actions, bom para debug e estados muito compartilhados.
URL: estado na URL é o mais importante pra SPA - filtros, paginação.
5-Como funciona o DOM virtual e quais são as suas vantagens?
É uma cópia leve do DOM real em memória (objeto JS).
Quando o estado muda, cria um novo Virtual DOM, compara com o anterior (diffing) e só atualiza no DOM real o que realmente mudou. 
Vantagem: DOM real é lento. Manipular objeto JS é muito mais rápido, evita re-render desnecessário.
6-O que é renderização do lado do servidor e quando você pode usá-la?
O HTML é gerado no servidor e enviado pronto pro navegador, ao invés de gerar tudo no cliente com JS.
Usar quando: precisa de SEO (Google lê melhor), performance inicial (First Contentful Paint rápido), redes sociais precisam de preview.
Não usar quando: dashboard altamente interativo, onde CSR é mais leve. Hoje o ideal é Next.js/Nuxt que fazem híbrido.
7-Como criar um layout de grade CSS?
Com CSS Grid:css.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr); /* 3 colunas iguais */
  gap: 16px;
}fr é fração, repeat repete, gap espaçamento. Usa grid-column / grid-row pra fazer item ocupar mais de uma célula.
8-Você pode explicar a especificidade do CSS e como ela funciona?
É a pontuação que decide qual regra vence.
Hierarquia: !important > inline style="" > #id (100) > .classe, :pseudo-classe, [atributo] (10) > elemento, ::pseudo-elemento (1)Ex: body #header .menu li = 1 + 100 + 10 + 1 = 112. Ganha de .menu li que é 11. Se empatar, vence a última declarada.
9-Como o navegador renderiza um site?
Parse HTML -> cria DOM
Parse CSS -> cria CSSOM
DOM + CSSOM = Render Tree (só o que vai ser visível)
Layout (reflow): calcula posição e tamanho de cada elemento.
Paint: pinta pixels.
Composite: junta as camadas na GPU.
Se você muda cor, só repinta. Se muda tamanho, refaz layout - é mais caro.
10-Faça um programa que receba a idade, o peso e o sexo de 10 pessoas. Calcule e imprima:
total de homens;
total de mulheres;
média das idades dos homens;
média dos pesos das mulheres.

Em JavaScript (roda no console/navegador):javascriptfunction calcularPessoas() {
  let totalHomens = 0;
  let totalMulheres = 0;
  let somaIdadeHomens = 0;
  let somaPesoMulheres = 0;

  for (let i = 1; i <= 10; i++) {
    let idade = parseInt(prompt(`Pessoa ${i} - Idade:`));
    let peso = parseFloat(prompt(`Pessoa ${i} - Peso:`));
    let sexo = prompt(`Pessoa ${i} - Sexo (M/F):`).toUpperCase();

    if (sexo === 'M') {
      totalHomens++;
      somaIdadeHomens += idade;
    } else if (sexo === 'F') {
      totalMulheres++;
      somaPesoMulheres += peso;
    }
  }

  let mediaIdadeHomens = totalHomens > 0 ? somaIdadeHomens / totalHomens : 0;
  let mediaPesoMulheres = totalMulheres > 0 ? somaPesoMulheres / totalMulheres : 0;

  console.log(`Total de homens: ${totalHomens}`);
  console.log(`Total de mulheres: ${totalMulheres}`);
  console.log(`Média das idades dos homens: ${mediaIdadeHomens.toFixed(1)}`);
  console.log(`Média dos pesos das mulheres: ${mediaPesoMulheres.toFixed(1)} kg`);
}

calcularPessoas();Se precisar em Python também, me fala que te mando.
