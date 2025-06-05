# 🎮 Guia Explicado: Jogo do Número Secreto com JavaScript

---

## 🧱 Boas-vindas ao Jogador

```javascript
alert('Olá, seja bem-vindo ao jogo do número secreto');
```

### 📝 Explicação:

* Um simples `alert()` pra mostrar uma mensagem de boas-vindas.

---

## 📦 Guardando Dados com Variáveis

```javascript
let numeroSecreto = 8;
let chute = prompt('Escolha um número entre 1 a 15');
```

### 📝 Explicação:

* `numeroSecreto` guarda o número fixo a ser adivinhado.
* `prompt()` coleta o chute do jogador e armazena na variável `chute`.

---

## 🔍 Comparando Chute e Resposta

```javascript
if (chute == numeroSecreto) {
  console.log('Parabéns, você acertou o número secreto (8)');
}
```

### 📝 Explicação:

* O `if` verifica se o chute é igual ao número secreto.
* Se sim, imprime no console uma mensagem de sucesso.

---

## ↔️ `else` e Comentários

```javascript
if (chute == numeroSecreto) {
  alert('Parabéns você acertou o número secreto');
} else {
  alert('Você errou o número secreto, tente novamente');
}
// Comentário: Este bloco verifica se o chute é igual ao número secreto.
```

### 📝 Explicação:

* `else` trata o caso de erro.
* Comentários ajudam a entender o que o código faz.

---

## 🧩 Template Strings

```javascript
alert(`Parabéns você acertou o número secreto ${numeroSecreto}`);
```

### 📝 Explicação:

* Template strings usam crases (`` ` ``) e `${}` para inserir variáveis diretamente dentro da string.

---

## 🌐 Live Server e Entrada Numérica

### 🔧 Melhorias:

* Instalar extensão **Live Server** no VS Code.
* Auto-atualização do navegador ao salvar.

```javascript
console.log = function() {}; // Desativa console.log

chute = parseInt(chute); // Ou:
chute = Number(chute);
```

### 📝 Explicação:

* Convertendo `chute` para número, já que `prompt()` retorna string.

---

## ⬆️⬇️ Dicas de Maior ou Menor

```javascript
if (chute > numeroSecreto){
  alert(`O número secreto é menor que ${chute}`);
} else {
  alert(`O número secreto é maior que ${chute}`);
}
```

### 📝 Explicação:

* Mostra se o número secreto está acima ou abaixo do chute.

---

## 🔁 Repetição com `while`

```javascript
while (chute != numeroSecreto) {
  chute = prompt('Escolha um número entre 1 e 15');
}
```

### 📝 Explicação:

* Repete o processo até acertar.

📌 **Operadores úteis:**

* `!=` diferente
* `==` igual
* `>` maior
* `>=` maior ou igual
* `++` incrementa 1

---

## 📊 Contador de Tentativas

```javascript
let tentativas = 1;

while (chute != numeroSecreto) {
  chute = prompt('Escolha um número entre 1 e 15');
  tentativas++;
}

alert(`Parabéns, você acertou com ${tentativas} tentativas`);
```

### 📝 Explicação:

* Conta quantas vezes o jogador tentou até acertar.

---

## ⛔ Interrompendo com `break`

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

### 📝 Explicação:

* Loop infinito com `while (true)`.
* Usa `break` para sair quando acertar.
* Ternário deixa a mensagem mais elegante.

---

## ⚖️ Ternário para Singular/Plural

```javascript
let palavraTentativas = tentativas > 1 ? 'tentativas' : 'tentativa';
alert(`Parabéns, você acertou com ${tentativas} ${palavraTentativas}!`);
```

### 📝 Explicação:

* Corrige gramática da mensagem final com operador ternário.

---

## 🎲 Número Aleatório

```javascript
let numeroAleatorio = Math.random();
```

### 📝 Explicação:

* Gera número decimal entre 0 e 1.

```javascript
let numero = Math.floor(Math.random() * 10) + 1;
```

* Agora sim: número inteiro entre 1 e 10.

---

## 🎯 Aleatório de 1 a 15

```javascript
let numeroSecreto = parseInt(Math.random() * 15 + 1);
```

### 📝 Explicação:

* Gera número inteiro entre 1 e 15, dinamicamente.

---

## 🧮 Número Máximo Configurável

```javascript
let numeroMaximo = 100;
let numeroSecreto = parseInt(Math.random() * numeroMaximo + 1);

while (chute != numeroSecreto) {
  chute = prompt(`Escolha um número entre 1 e ${numeroMaximo}`);
}
```

### 📝 Explicação:

* Torna o jogo escalável.
* Fácil mudar o limite do jogo apenas ajustando uma variável.

---

## 🏁 Conclusão Final

Esse projeto ensina de forma prática:

✅ Variáveis e entrada de dados
✅ Condicionais (`if/else`)
✅ Laços (`while`)
✅ Conversão de dados (string → número)
✅ Operadores lógicos e ternário
✅ Geração de número aleatório
✅ Organização de código com boas práticas

---
