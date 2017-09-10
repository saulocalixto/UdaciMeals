# ANOTAÇÕES DURANTE AS AULAS

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

[thunk]: <https://classroom.udacity.com/nanodegrees/nd019/parts/a4275a36-bab7-4cbe-a9b0-dead70fceed2/modules/c9705bac-9eb4-48b2-983b-d986eb5d215e/lessons/84a3ef1e-8dc3-4608-8547-36c14c79e1f6/concepts/b38d3114-a042-4be9-995f-73729b413df9>
[Mais Middlewares]: <https://github.com/xgrommx/awesome-redux>
[Exemplos de Projetos Redux]: <http://redux.js.org/docs/introduction/Examples.html>
[Especificações para projeto final]: <https://classroom.udacity.com/nanodegrees/nd019/parts/a4275a36-bab7-4cbe-a9b0-dead70fceed2/modules/1cccfc2d-c00b-496a-9814-0f8359b19809/lessons/ebe0358d-de4e-4a88-91ca-27b9fa77326e/concepts/2fbcdc1b-5981-445f-8ef2-6fbecc5a416a>
