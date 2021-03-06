---
id: aa2e6f85cab2ab736c9a9b24
title: Cash Register
isRequired: true
challengeType: 5
videoUrl: ''
localeTitle: Caixa registradora
---

## Description
<section id="description"> <code>checkCashRegister()</code> função de gaveta de caixa registradora <code>checkCashRegister()</code> que aceita o preço de compra como primeiro argumento ( <code>price</code> ), pagamento como o segundo argumento ( <code>cash</code> ) e gaveta com dinheiro ( <code>cid</code> ) como o terceiro argumento. <code>cid</code> é um array 2D listando a moeda disponível. A função <code>checkCashRegister()</code> deve sempre retornar um objeto com uma chave de <code>status</code> e uma chave de <code>change</code> . Retornar <code>{status: &quot;INSUFFICIENT_FUNDS&quot;, change: []}</code> se a gaveta do caixa for menor que a alteração devida ou se você não puder devolver a alteração exata. Retornar <code>{status: &quot;CLOSED&quot;, change: [...]}</code> com gaveta do caixa como o valor para a <code>change</code> da chave, se for igual à alteração devida. Caso contrário, retorne <code>{status: &quot;OPEN&quot;, change: [...]}</code> , com a alteração devida em moedas e faturas, classificada na ordem mais alta para a mais baixa, como o valor da chave de <code>change</code> . Lembre-se de usar <a href="http://forum.freecodecamp.org/t/how-to-get-help-when-you-are-stuck/19514" target="_blank">Read-Search-Ask</a> se você ficar preso. Tente emparelhar o programa. Escreva seu próprio código. <table class="table table-striped"><tbody><tr><th> Unidade monetária </th><th> Montante </th></tr><tr><td> Centavo </td><td> US $ 0,01 (PENNY) </td></tr><tr><td> Níquel </td><td> US $ 0,05 (NICKEL) </td></tr><tr><td> Centavo </td><td> US $ 0,1 (DIME) </td></tr><tr><td> Trimestre </td><td> US $ 0,25 (TRIMESTRE) </td></tr><tr><td> Dólar </td><td> US $ 1 (DÓLAR) </td></tr><tr><td> Cinco dólares </td><td> US $ 5 (cinco) </td></tr><tr><td> Dez dólares </td><td> US $ 10 (DEZ) </td></tr><tr><td> Vinte dólares </td><td> US $ 20 (VINTE) </td></tr><tr><td> Cem dólares </td><td> US $ 100 (cem) </td></tr></tbody></table></section>

## Instructions
<section id="instructions">
</section>

## Tests
<section id='tests'>

```yml
tests:
  - text: '<code>checkCashRegister(19.5, 20, [[&quot;PENNY&quot;, 1.01], [&quot;NICKEL&quot;, 2.05], [&quot;DIME&quot;, 3.1], [&quot;QUARTER&quot;, 4.25], [&quot;ONE&quot;, 90], [&quot;FIVE&quot;, 55], [&quot;TEN&quot;, 20], [&quot;TWENTY&quot;, 60], [&quot;ONE HUNDRED&quot;, 100]])</code> devem retornar um objeto.'
    testString: 'assert.deepEqual(Object.prototype.toString.call(checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]])), "[object Object]", "<code>checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]])</code> should return an object.");'
  - text: '<code>checkCashRegister(19.5, 20, [[&quot;PENNY&quot;, 1.01], [&quot;NICKEL&quot;, 2.05], [&quot;DIME&quot;, 3.1], [&quot;QUARTER&quot;, 4.25], [&quot;ONE&quot;, 90], [&quot;FIVE&quot;, 55], [&quot;TEN&quot;, 20], [&quot;TWENTY&quot;, 60], [&quot;ONE HUNDRED&quot;, 100]])</code> devem retornar <code>{status: &quot;OPEN&quot;, change: [[&quot;QUARTER&quot;, 0.5]]}</code> .'
    testString: 'assert.deepEqual(checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]), {status: "OPEN", change: [["QUARTER", 0.5]]}, "<code>checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]])</code> should return <code>{status: "OPEN", change: [["QUARTER", 0.5]]}</code>.");'
  - text: '<code>checkCashRegister(3.26, 100, [[&quot;PENNY&quot;, 1.01], [&quot;NICKEL&quot;, 2.05], [&quot;DIME&quot;, 3.1], [&quot;QUARTER&quot;, 4.25], [&quot;ONE&quot;, 90], [&quot;FIVE&quot;, 55], [&quot;TEN&quot;, 20], [&quot;TWENTY&quot;, 60], [&quot;ONE HUNDRED&quot;, 100]])</code> devem retornar <code>{status: &quot;OPEN&quot;, change: [[&quot;TWENTY&quot;, 60], [&quot;TEN&quot;, 20], [&quot;FIVE&quot;, 15], [&quot;ONE&quot;, 1], [&quot;QUARTER&quot;, 0.5], [&quot;DIME&quot;, 0.2], [&quot;PENNY&quot;, 0.04]]}</code> .'
    testString: 'assert.deepEqual(checkCashRegister(3.26, 100, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]), {status: "OPEN", change: [["TWENTY", 60], ["TEN", 20], ["FIVE", 15], ["ONE", 1], ["QUARTER", 0.5], ["DIME", 0.2], ["PENNY", 0.04]]}, "<code>checkCashRegister(3.26, 100, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]])</code> should return <code>{status: "OPEN", change: [["TWENTY", 60], ["TEN", 20], ["FIVE", 15], ["ONE", 1], ["QUARTER", 0.5], ["DIME", 0.2], ["PENNY", 0.04]]}</code>.");'
  - text: '<code>checkCashRegister(19.5, 20, [[&quot;PENNY&quot;, 0.01], [&quot;NICKEL&quot;, 0], [&quot;DIME&quot;, 0], [&quot;QUARTER&quot;, 0], [&quot;ONE&quot;, 0], [&quot;FIVE&quot;, 0], [&quot;TEN&quot;, 0], [&quot;TWENTY&quot;, 0], [&quot;ONE HUNDRED&quot;, 0]])</code> devem retornar <code>{status: &quot;INSUFFICIENT_FUNDS&quot;, change: []}</code> .'
    testString: 'assert.deepEqual(checkCashRegister(19.5, 20, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]]), {status: "INSUFFICIENT_FUNDS", change: []}, "<code>checkCashRegister(19.5, 20, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])</code> should return <code>{status: "INSUFFICIENT_FUNDS", change: []}</code>.");'
  - text: '<code>checkCashRegister(19.5, 20, [[&quot;PENNY&quot;, 0.01], [&quot;NICKEL&quot;, 0], [&quot;DIME&quot;, 0], [&quot;QUARTER&quot;, 0], [&quot;ONE&quot;, 1], [&quot;FIVE&quot;, 0], [&quot;TEN&quot;, 0], [&quot;TWENTY&quot;, 0], [&quot;ONE HUNDRED&quot;, 0]])</code> devem retornar <code>{status: &quot;INSUFFICIENT_FUNDS&quot;, change: []}</code> .'
    testString: 'assert.deepEqual(checkCashRegister(19.5, 20, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 1], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]]), {status: "INSUFFICIENT_FUNDS", change: []}, "<code>checkCashRegister(19.5, 20, [["PENNY", 0.01], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 1], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])</code> should return <code>{status: "INSUFFICIENT_FUNDS", change: []}</code>.");'
  - text: '<code>checkCashRegister(19.5, 20, [[&quot;PENNY&quot;, 0.5], [&quot;NICKEL&quot;, 0], [&quot;DIME&quot;, 0], [&quot;QUARTER&quot;, 0], [&quot;ONE&quot;, 0], [&quot;FIVE&quot;, 0], [&quot;TEN&quot;, 0], [&quot;TWENTY&quot;, 0], [&quot;ONE HUNDRED&quot;, 0]])</code> devem retornar <code>{status: &quot;CLOSED&quot;, change: [[&quot;PENNY&quot;, 0.5], [&quot;NICKEL&quot;, 0], [&quot;DIME&quot;, 0], [&quot;QUARTER&quot;, 0], [&quot;ONE&quot;, 0], [&quot;FIVE&quot;, 0], [&quot;TEN&quot;, 0], [&quot;TWENTY&quot;, 0], [&quot;ONE HUNDRED&quot;, 0]]}</code> .'
    testString: 'assert.deepEqual(checkCashRegister(19.5, 20, [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]]), {status: "CLOSED", change: [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]]}, "<code>checkCashRegister(19.5, 20, [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])</code> should return <code>{status: "CLOSED", change: [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]]}</code>.");'

```

</section>

## Challenge Seed
<section id='challengeSeed'>

<div id='js-seed'>

```js
function checkCashRegister(price, cash, cid) {
  var change;
  // Here is your change, ma'am.
  return change;
}

// Example cash-in-drawer array:
// [["PENNY", 1.01],
// ["NICKEL", 2.05],
// ["DIME", 3.1],
// ["QUARTER", 4.25],
// ["ONE", 90],
// ["FIVE", 55],
// ["TEN", 20],
// ["TWENTY", 60],
// ["ONE HUNDRED", 100]]

checkCashRegister(19.5, 20, [["PENNY", 1.01], ["NICKEL", 2.05], ["DIME", 3.1], ["QUARTER", 4.25], ["ONE", 90], ["FIVE", 55], ["TEN", 20], ["TWENTY", 60], ["ONE HUNDRED", 100]]);

```

</div>



</section>

## Solution
<section id='solution'>

```js
// solution required
```
</section>
