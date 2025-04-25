# Guia Completo: Jogo de Adivinhação em JavaScript

Este é um jogo simples de adivinhação, onde o usuário precisa tentar descobrir um número secreto gerado aleatoriamente pelo sistema. O jogo fornece dicas informando se o número escolhido pelo jogador é maior ou menor que o número secreto.

---

## Aula 1: Introdução ao Projeto

**Objetivo:** Criar o esqueleto básico do jogo.

```javascript
alert('Olá, seja bem-vindo ao jogo do número secreto');
```

---

## Aula 2: Variáveis e Entrada do Usuário

**Objetivo:** Definir variáveis e coletar dados do usuário.

```javascript
let numeroSecreto = 8;
let chute = prompt('Escolha um número entre 1 a 15');
```

---

## Aula 3: Condições e Comparações

**Objetivo:** Comparar valores e executar ações com base nessa comparação.

```javascript
if (chute == numeroSecreto) {
  console.log('Parabéns, você acertou o número secreto (8)');
}
```

---

## Aula 4: `else` e Comentários

**Objetivo:** Implementar lógica com `else` e adicionar comentários ao código.

```javascript
if (chute == numeroSecreto) {
  alert('Parabéns você acertou o número secreto');
} else {
  alert('Você errou o número secreto, tente novamente');
}
// Comentário: Este bloco verifica se o chute é igual ao número secreto.
```

---

## Aula 5: Concatenação e Template Strings

**Objetivo:** Melhorar as mensagens com template strings.

```javascript
alert(`Parabéns você acertou o número secreto ${numeroSecreto}`);
```

---

## Aula 6: Live Server no VS Code

**Objetivo:** Atualizar automaticamente o navegador ao editar o código.

- Instalar a extensão Live Server.
- Com ela, o navegador atualiza automaticamente a cada modificação.

**Melhorias:**

- Desabilitar `console.log`:  
```javascript
console.log = function() {};
```
- Converter entrada com `parseInt` ou `Number`:  
```javascript
chute = parseInt(chute);
// ou
chute = Number(chute);
```

---

## Aula 7: Dicas de "maior" ou "menor"

**Objetivo:** Indicar se o número secreto é maior ou menor que o chute.

```javascript
if (chute > numeroSecreto){
  alert(`O número secreto é menor que ${chute}`);
} else {
  alert(`O número secreto é maior que ${chute}`);
}
```

---

## Aula 8: Estrutura de Repetição

**Objetivo:** Repetir o jogo até o número secreto ser descoberto.

```javascript
while (chute != numeroSecreto) {
  chute = prompt('Escolha um número entre 1 e 15');
}
```

**Operadores de Comparação:**
- `!=` diferente  
- `==` igual  
- `>` maior  
- `>=` maior ou igual  
- `++` incrementa 1

---

## Aula 9: Contador de Tentativas

**Objetivo:** Informar quantas tentativas foram necessárias.

```javascript
let tentativas = 1;

while (chute != numeroSecreto) {
  chute = prompt('Escolha um número entre 1 e 15');
  tentativas++;
}

alert(`Parabéns, você acertou com ${tentativas} tentativas`);
```

---

## Aula 10: `break` para interromper o loop

**Objetivo:** Parar o loop assim que o número for acertado.

```javascript
while (true) {
  let chute = prompt('Digite o número secreto:');

  if (chute == numeroSecreto) {
    break;
  } else {
    alert(`O número secreto é ${chute > numeroSecreto ? 'menor' : 'maior'} que ${chute}`);
  }

  tentativas++;
}

alert(`Parabéns, você acertou com ${tentativas} ${tentativas > 1 ? 'tentativas' : 'tentativa'}!`);
```

---

## Aula 11: Operador Ternário

**Objetivo:** Usar o ternário para decidir entre singular ou plural.

```javascript
let palavraTentativas = tentativas > 1 ? 'tentativas' : 'tentativa';
alert(`Parabéns, você acertou com ${tentativas} ${palavraTentativas}!`);
```

---

## Aula 12: `Math.random()`

**Objetivo:** Gerar número aleatório entre 0 e 1.

```javascript
let numeroAleatorio = Math.random();
```

Para gerar de 1 a 10:

```javascript
let numero = Math.floor(Math.random() * 10) + 1;
```

---

## Aula 13: Número aleatório inteiro de 1 a 15

```javascript
let numeroSecreto = parseInt(Math.random() * 15 + 1);
```

---

## Aula 14: Número máximo customizável

```javascript
let numeroMaximo = 100;
let numeroSecreto = parseInt(Math.random() * numeroMaximo + 1);

while (chute != numeroSecreto) {
  chute = prompt(`Escolha um número entre 1 e ${numeroMaximo}`);
}
```

---

## Fim!

Esse foi o passo a passo da criação de um jogo de adivinhação completo em JavaScript, com boas práticas e interatividade para o usuário.
