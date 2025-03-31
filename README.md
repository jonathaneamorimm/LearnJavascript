# Conteudo referente a trilha de Javascript

## Conteudo básico
- Curso básico de Javascript - CodeAcademy
  - Funções de impressão (console.log, alert);
  - Escopo de variáveis e constantes (let, var, const)
  - Estruturas condicionais (if, else);
  - Estruturas de repetição (for, while);
  - Declarar e operar as funções na linguagem;
  - Arrow function (ECMA-5);
  - Comprovação
![Code Academy](/assets/codeAcademy.png)

- Curso de Javascript do Gustavo Guanabara
  - [Acessar Playlist](https://www.youtube.com/playlist?list=PLHz_AreHm4dlsK3Nr9GVvXCbpQyHQl1o1)

 
## Conteudo Médio
- Requisições AJAX
  - pt-br: API REST com JSON Server, Requisições
  - inglês: Create a fake REST API with JSON-Server
    - [Video sobre api Rest com JSON Server](https://www.fabricadecodigo.com/json-server/)
    - [Documentação Oficial Json-server](https://www.npmjs.com/package/json-server)
    - Detalhamento FETCH:
      - O fetch é um método do nativo do Javascript que permite realizar requisições HTTP sem a necessidade de bibliotecas ou frameworks externos. O método fetch é um método assíncrono que retorna uma promisse. Existem duas formas de trabalhar com o fetch:
        - A primeira forma é utilizando o fetch().then o qual é uma maneira simplificada de realizar a operação assíncrona.
          ```
          fetch('http://simulation.request.com/users', config)
          .then(res => res.json())
          .then(response => console.log(response))
          .catch(err => console.log(err));
          ```
        - A outra forma de utilizar é utilizando o ASYNC/AWAIT. Essa forma é ama forma mais limpa e legível de visualizar uma requisição utilizando o fetch.
          ```
          async function getUser() {
            try {
              const response = await fetch('http://simulation.request.com/users', config);
              // inserir exceções para tratamento de erro
              const dados = await response.json();
              console.log(dados);
            } catch (err) {
              console.log(err);
            }
          }
          ``` 
        - Documentação sobre as respostas do fetch: [Fetch responses](https://developer.mozilla.org/pt-BR/docs/Web/API/Response)
        - [Exemplo de utilização do FETCH](/test/JsonServer/src/js/services/api.js);
- Promises, async/await
  - pt-br: Requisições AJAX com JavaScript
  - inglês: Javascript Promises
    - Detalhamento ASYNC/AWAIT:
      - O `async` e o `await` são utilizados para trabalhar com código assíncrono, ou seja, aquele em que algumas operações podem ser iniciadas e, enquanto aguardam a conclusão o programa continua executando outras tarefas. Resumidamente eles servem para não travar a execução do codigo enquanto aguarda o resultado dessas operações.
        ```
            // Exemplo de codigo síncrono
            console.log('Inicio'); // Exibe o primeiro console
            alert('Meio'); // Trava o programa para exibir o alert
            console.log('Fim'); // Apos o alert ser fechado exibe o ultimo console
        ``` 
        Nesse exemplo, o código fica bloqueado esperando o usuário fechar o alert, o que impede que a linha console.log('Fim') seja executada até isso acontecer.

        ```
            // Mesmo exemplo só que utilizando um código assíncrono 
            console.log("Início"); // Exibe o primeiro console
            setTimeout(() => {
                console.log("Fim");
            }, 2000); // Vai esperar 2 segundos antes de exibir "Fim", mas o código continua executando enquanto isso

            console.log("Meio"); // Vai exibir o console após o inicio
        ```
        Aqui, o código não fica bloqueado. Ele começa a execução da função setTimeout e continua com console.log("Meio") enquanto aguarda a conclusão do setTimeout. O "Fim" só é exibido após 2 segundos, mas o programa não foi "travado" enquanto isso.
        - [Exemplo de utilização do ASYNC|AWAIT](/test/JsonServer/src/js/services/api.js);

    - Detalhamento Promisses:
      - Podemos comparar a promisse como uma promessa de algo que vai acontecer no futuro. São utilizadas no JS para representar uma ação ASSINCRONA, ou seja, como explicado anteriormente é algo que não acontece imediatamente.
      - A promisse possui 3 estados principais:
        - Pending(Em espera): Quando você cria uma Promisse, ela começa no estado de pending. Significa que o que você pediu ainda está sendo feito.
        - Fulfilled (Cumprida): Quando a operação assincrona é concluida. No caso você recebe o que foi prometido.
        - Rejected (Reijeitada): Se algo der errado e a operação nao puder ser concluida, a Promisse é rejeitada.
      - Promisse é uma classe padrão no Javascript, a qual outras classes utilizam suas propriedades como é o caso do FETCH que é uma função nativa do JS que retorna uma Promisse(class).
      - [Exemplo de utilização da Classe Promisse](/test/Promisse/promisse.js)
- Manipulação DOM
  - inglês: The Document Object Model
- Event Propagation/Event Bubbling
  - inglês: Event Bubbling (MDN)
- GULP
## Conteudo avançado
- Node.js: o que é, como funciona
- Entendendo o npm e seus principais comandos (npm init, npm install, npm run);
- Entendendo automatizadores de tarefas e uso de Gulp.
- O que é Babel.js e para que serve