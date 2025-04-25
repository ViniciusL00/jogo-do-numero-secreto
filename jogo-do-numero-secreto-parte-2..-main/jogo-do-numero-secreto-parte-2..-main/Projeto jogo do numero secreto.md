# 🚀 Curso: Lógica de Programação com JavaScript (Parte 2)

---

## 🧠 Aula 1: Manipulação de Textos

**Objetivo:**  
Modificar conteúdo de elementos HTML usando JavaScript.

### ✏️ Exemplo 1: Alterando um título (h1)

```javascript
let titulo = document.querySelector('h1');
titulo.innerHTML = 'Jogo do Número Secreto';
```

### ✏️ Exemplo 2: Alterando um parágrafo (p)

```javascript
let paragrafo = document.querySelector('p');
paragrafo.innerHTML = 'Escolha um número entre 1 a 100';
```

---

## ⚙️ Aula 2: Criando uma Função

**Objetivo:**  
Vincular uma função JavaScript a um clique de botão.

### 🧩 HTML

```html
<button onclick="verificarChute()">Chutar</button>
```

### 🧩 JavaScript

```javascript
function verificarChute() {
  console.log('O botão foi clicado!');
}
```

---

## 🔁 Aula 3: Funções com Parâmetros

**Objetivo:**  
Evitar repetição de código com funções reutilizáveis.

### 🛠️ Função

```javascript
function exibirTextoNaTela(tag, texto){
  let campo = document.querySelector(tag);
  campo.innerHTML = texto;
}
```

### 🧪 Uso

```javascript
exibirTextoNaTela('h1', 'Jogo do Número Secreto');
exibirTextoNaTela('p', 'Escolha um número entre 1 a 100');
```

---

## 🎲 Aula 4: Funções com Retorno

**Objetivo:**  
Gerar número aleatório para o jogo.

```javascript
function gerarNumeroAleatorio() {
  return parseInt(Math.random() * 100 + 1);
}
```

---

## 🧾 Aula 5: Tipo Booleano

**Objetivo:**  
Comparar valor do chute com o número secreto.

```javascript
let chute = document.querySelector('input').value;
console.log(chute == numeroSecreto);
```

---

## ✅ Aula 6: Verificando o Chute

**Objetivo:**  
Verificar se o usuário acertou, errou, e dar feedback.

```javascript
function verificarChute() {
  let chute = document.querySelector('input').value;

  if (chute == numeroSecreto){
    exibirTextoNaTela('h1', 'Acertou!');
    exibirTextoNaTela('p', 'Parabéns você descobriu o número secreto!');
  } else {
    if (chute > numeroSecreto){
      exibirTextoNaTela('p', 'O número secreto é menor');
    } else {
      exibirTextoNaTela('p', 'O número secreto é maior');
    }
  }
}
```

---

## 📊 Aula 7: Contando Tentativas

**Objetivo:**  
Mostrar quantas tentativas o usuário fez até acertar.

```javascript
function verificarChute() {
  let chute = document.querySelector('input').value;

  if (chute == numeroSecreto) {
    exibirTextoNaTela('h1', 'Acertou!');
    let palavraTentativa = tentativas > 1 ? 'Tentativas' : 'tentativa';
    let mensagemTentativas = `Parabéns, você descobriu o número secreto com ${tentativas} ${palavraTentativa}!`;
    exibirTextoNaTela('p', mensagemTentativas);
  } else {
    if (chute > numeroSecreto) {
      exibirTextoNaTela('p', 'O número secreto é menor');
    } else {
      exibirTextoNaTela('p', 'O número secreto é maior');
    }
    tentativas += 1;
  }
}
```

---

## 🔁 Aula 8: Botão de Reiniciar

**Objetivo:**  
Permitir reiniciar o jogo após acerto.

### 🧹 Função para limpar o campo

```javascript
function limparCampo() {
  document.querySelector('input').value = '';
}
```

### 🧼 Atualização na verificação do chute

```javascript
limparCampo();
```

### 🆕 Ativar botão "Novo Jogo" quando acertar

```javascript
document.getElementById('reiniciar').removeAttribute('disabled');
```

---

## 🕹️ Aula 9: Reiniciando o Jogo

**Objetivo:**  
Resetar o jogo com novo número e tentativas.

### 💻 HTML

```html
<button onclick="reiniciarJogo()" id="reiniciar" disabled>Novo jogo</button>
```

### 🔄 JavaScript

```javascript
function reiniciarJogo() {
  numeroSecreto = gerarNumeroAleatorio();
  limparCampo();
  tentativas = 1;
  exibirMensagemInicial();
  document.getElementById('reiniciar').setAttribute('disabled', true);
}

function exibirMensagemInicial() {
  exibirTextoNaTela('h1', 'Jogo do Número Secreto');
  exibirTextoNaTela('p', 'Escolha um número entre 1 e 100');
}
```

---

## 🧠 Aula 10: Lista de Números Sorteados

**Objetivo:**  
Evitar repetição de números ao sortear.

### 📋 Lista

```javascript
let listaNumerosSorteados = [];
```

### 🧮 Atualização na função de gerar número

```javascript
function gerarNumeroAleatorio() {
  let numeroEscolhido = parseInt(Math.random() * 100 + 1);

  if (listaNumerosSorteados.includes(numeroEscolhido)) {
    return gerarNumeroAleatorio();
  } else {
    listaNumerosSorteados.push(numeroEscolhido);
    return numeroEscolhido;
  }
}
```
