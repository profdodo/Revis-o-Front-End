Respostas da atividade de revisão 

### 1. O que são variáveis CSS e quando você as usaria?

São valores que podemos guardar no CSS para usar várias vezes. Eu usaria principalmente para cores, fontes e tamanhos, porque facilita quando preciso mudar alguma coisa no site.

### 2. Como funciona o loop de eventos em JavaScript?

O loop de eventos permite que o JavaScript execute tarefas enquanto espera outras operações terminarem. Assim, o programa não fica travado esperando uma tarefa.

### 3. Quais são as diferentes maneiras de lidar com operações assíncronas em JavaScript?

As principais formas são **Callbacks, Promises e Async/Await**. Elas servem para trabalhar com tarefas que demoram um tempo para terminar, como buscar dados de uma API.

### 4. Como gerenciar o estado em aplicações de página única?

O estado pode ser gerenciado usando variáveis, objetos, `localStorage` ou bibliotecas como Redux. Ele serve para guardar informações que podem mudar durante o uso da aplicação.

### 5. Como funciona o DOM virtual e quais são as suas vantagens?

O DOM virtual é uma cópia do DOM que fica na memória. Quando alguma coisa muda, ele verifica o que realmente precisa ser alterado na página. Isso ajuda a melhorar o desempenho.

### 6. O que é renderização do lado do servidor e quando você pode usá-la?

É quando o servidor prepara o HTML da página antes de enviar para o navegador. Pode ser usada para melhorar o carregamento da página e também o SEO.

### 7. Como criar um layout de grade CSS?

Podemos usar o **CSS Grid**, colocando `display: grid` no elemento e definindo as colunas.

```css
.container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

### 8. Você pode explicar a especificidade do CSS e como ela funciona?

A especificidade define qual regra CSS terá prioridade quando existem várias regras para o mesmo elemento. Por exemplo, uma classe geralmente tem prioridade maior que um seletor de elemento.

### 9. Como o navegador renderiza um site?

Primeiro o navegador recebe o HTML, CSS e JavaScript. Depois ele monta a estrutura da página, aplica os estilos, calcula a posição dos elementos e finalmente mostra tudo na tela.

### 10. Programa para 10 pessoas

```javascript
let homens = 0;
let mulheres = 0;
let somaIdadeHomens = 0;
let somaPesoMulheres = 0;

for (let i = 1; i <= 10; i++) {
    let idade = Number(prompt("Digite a idade:"));
    let peso = Number(prompt("Digite o peso:"));
    let sexo = prompt("Digite o sexo (M/F):").toUpperCase();

    if (sexo === "M") {
        homens++;
        somaIdadeHomens += idade;
    } else if (sexo === "F") {
        mulheres++;
        somaPesoMulheres += peso;
    }
}

let mediaIdade = homens > 0 ? somaIdadeHomens / homens : 0;
let mediaPeso = mulheres > 0 ? somaPesoMulheres / mulheres : 0;

console.log("Total de homens:", homens);
console.log("Total de mulheres:", mulheres);
console.log("Média das idades dos homens:", mediaIdade);
console.log("Média dos pesos das mulheres:", mediaPeso);
```

ele pede os dados de 10 pessoas, separa homens e mulheres e depois calcula as médias solicitadas.
