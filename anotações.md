# ANOTAÇÕES DURANTE AS AULAS

### Redux

*O objetivo principal do Redux é fazer com que o gerenciamento de estado do seu aplicativo seja mais manejável. Tipicamente, você usaria Redux em combinação com o React. Entretanto, eles não precisam ser usados em conjunto. O Redux pode ser usado, na verdade, por qualquer aplicativo que precise de ajuda para gerenciar seu estado.*

![imgRedux]

Este é o gráfico que acabamos de ver. Como você pode ver, existem três partes principais no Redux:

* actions
* reducers
* store

A maior parte dos dados ou estado do aplicativo vive na store. Os dados da store são preenchidos por reducers (é possível ter mais de um reducer, mas estamos apenas mostrando um na imagem). Uma action é “despachada” pela store, e é o que é usada pelos reducers para determinar quais dados eles devem produzir. Para ser mais claro, pode (e vai!) haver mais de uma única action em um aplicativo Redux.

#### Actions
O Redux, assim como o navegador, permite que você configure listeners para responder a determinados eventos, mas, no Redux, esses eventos são chamado de actions. Actions são pacotes de informação que você configura para descrever qualquer evento de seu aplicativo que deva atualizar o estado dele.

```javascript
const CREATE_MEAL = 'CREATE_MEAL';
function mealCreator(id) {
    return {
        type: CREATE_MEAL,
        id: id
    }
}
```
#### Reducers
Um reducer recebe o estado atual e uma action que foi despachada e, então, decide como transformar o estado atual em um estado novinho em folha, baseado na action que recebeu.

```javascript
function reducer (state, action) {
  switch (action.type) {
    case 'SUBMIT_USER' :
      return Object.assign({}, state, {
        user: action.user
      })
  }
}
```
**Um reducer é uma função pura**

* Retornam sempre o mesmo resultado quando um mesmo conjunto de argumentos é passado a elas;
* Dependem apenas dos argumentos passados a elas;
* Não produzem efeitos colaterais.

#### Store
Store representa uma single source of truth. Isso é, a store contém um estado global do aplicativo, tudo guardado em uma única árvore de objetos. No geral, se um estado é compartilhado e pode ser acessado por todo o aplicativo, ele deve ser mantido na store.

Para criar uma store, você passa uma função reducer como o primeiro argumento para o método `createStore()` do Redux. O que é retornado pelo `createStore()` é a próprio store. Essa store tem três propriedades:

* `getState()`

>*  Não Recebe nenhum parâmetro e retorna o estado atual da store.

* `dispatch()`

>*  Recebe um objeto da action e chama a função reducer, passando o estado atual e a action que foi despachada para ela.

* `subscribe()`

>* Recebe uma função listener de callback que será invocada sempre que o estado da store for alterado.

### Middleware Thunk
Se um aplicativo requer interação com um servidor, usar um middleware como o `thunk` ajuda a resolver o problema do fluxo de dados assíncrono. O thunk nos permite escrever action creators assíncronos que retornam funções (em vez de objetos). O thunk pode, então, ser usado para atrasar o despacho de uma action ou para despachar somente se uma certa condição for satisfeita (ex: um pedido é resolvido).

**Como usar:**

`$ npm install --save redux-thunk`

`import thunk from 'redux-thunk'`

*Mais informações:* [thunk]

#### Projeto Final
[Especificações para projeto final]

### Links Úteis
[Mais Middlewares]

[Exemplos de Projetos Redux]

[imgRedux]: <https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59811293_nd019-c2-redux-full/nd019-c2-redux-full.png>
[thunk]: <https://classroom.udacity.com/nanodegrees/nd019/parts/a4275a36-bab7-4cbe-a9b0-dead70fceed2/modules/c9705bac-9eb4-48b2-983b-d986eb5d215e/lessons/84a3ef1e-8dc3-4608-8547-36c14c79e1f6/concepts/b38d3114-a042-4be9-995f-73729b413df9>
[Mais Middlewares]: <https://github.com/xgrommx/awesome-redux>
[Exemplos de Projetos Redux]: <http://redux.js.org/docs/introduction/Examples.html>
[Especificações para projeto final]: <https://classroom.udacity.com/nanodegrees/nd019/parts/a4275a36-bab7-4cbe-a9b0-dead70fceed2/modules/1cccfc2d-c00b-496a-9814-0f8359b19809/lessons/ebe0358d-de4e-4a88-91ca-27b9fa77326e/concepts/2fbcdc1b-5981-445f-8ef2-6fbecc5a416a>
