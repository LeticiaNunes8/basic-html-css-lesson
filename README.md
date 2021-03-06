# basic-html-css-lesson

### Desafio: Vamos construir um perfil cópia do Instagram 📸!

### NIVEL 1
- Deixe esse perfil bonito e maneiro. Cores mais legais, talvez sombras, bordas arredondas e o que mais você achar legal. Vale se inspirar em sites já existentes, como Github ou Airbnb.

### NIVEL 2
- As imagens e botões devem parecer legal no celular. Que tal usar media queries e flex-box? Ou quem sabe grids?
- Adicionar fotos com texto e que elas sejam responsivas.
- Talvez usar uma font do Google Fonts?

### NIVEL 3
- Ao clicar em "solicitar amizade" o botão deve mudar de texto e estilo, você pode fazer isto adicionando uma classe e usando funções como innerText.
- Ao clicar em "enviar mensagem" a div com id "message" deve aparecer.

### NIVEL 4
- Ao clicar em salvar um evento o texto deve mudar para "salvo" e o estilo do botão também deve mudar.

### NIVEL 5
- Toda vez que você clicar em salvar um botão o contador de "salvos" deve atualizar sua contagem.

---------------------------

## CHEATSHEET JS

#### Selecionar um elemento no DOM

##### Selecionando um id 
```
# HTML
<div id="um-id-qualquer">Oi</div>

#JS
document.querySelector("#um-id-qualquer")
```

#### Selecionar uma classe
```
# HTML
<div class="uma-classe-qualquer">Oi</div>

#JS
document.querySelector(".uma-classe-qualquer")
```

#### Selecionar vários elementos
```
# HTML
<div class="uma-classe-qualquer">Oi</div>
<div class="uma-classe-qualquer">Olá</div>

#JS
document.querySelectorAll(".uma-classe-qualquer")
```

#### Atribuir um elemento DOM a uma variável ou constante
##### Variável -> se eu for mudar o valor depois, mas sempre dê preferência por usar constantes
`let meuElementoLindo = document.querySelector("#um-id-qualquer")`

##### Constante
`const meuElementoLindo = document.querySelector("#um-id-qualquer")`

#### Modificar os atributos ou estilo do elemento
**Mudar o texto:** `meuElementoLindo.innerText = 'Um outro texto qualquer'`

**Mudar o HTML:** `meuElementoLindo.innerHTML = '<b>Um outro texto qualquer</b>'`

**Adicionar uma classe:** `meuElementoLindo.classList.add('uma-classe-qualquer')`. Não precisa adicionar o `.` pois aqui a função já sabe que você quer uma classe.

**Ler um [*data attribute*](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Howto/Use_data_attributes):** 
```
# HTML
<div id="um-id-qualquer" data-atributo-maneiro="qualquer coisa, desde strings, booleans, numeros...">

#JS
meuElementoLindo.dataset.atributoManeiro
```

**Definir um [*data attribute*](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Howto/Use_data_attributes):** 
```
# HTML ANTES
<div id="um-id-qualquer" data-atributo-maneiro="true">

# JS
meuElementoLindo.dataset.atributoManeiro = 'false'

# HTML DEPOIS
<div id="um-id-qualquer" data-atributo-maneiro="false">
```

**Mudar um estilo do elemento, vulgo CSS** 
`meuElementoLindo.style.nomeDoAtributoCSSEscritoAssim = "algum valor válido"`
Exs:
```
meuElementoLindo.style.backgroundColor = "red"
meuElementoLindo.style.display = "none"
meuElementoLindo.style.opacity = "0"
meuElementoLindo.style.marginTop = "10px"
```

**Ler  um estilo do elemento, vulgo CSS** 
`getComputedStyle(meuElementoLindo).nomeDoAtributoCSSEscritoAssim`
Exs:
```
getComputedStyle(meuElementoLindo).backgroundColor
getComputedStyle(meuElementoLindo).display
getComputedStyle(meuElementoLindo).opacity
getComputedStyle(meuElementoLindo).marginTop
```

**Adicionar um receptor de evento, quando o usuário faz alguma coisa ou o browser faz, a um elemento**
Com isso vamos conseguir fazer algo quando o usuário clicar em algo, passar o mouse ou o browser carregar tudo ou mesmo ficar sem internet. Cada eventos destes recebe um nome que alguém inventou ou que nós mesmos podemos criar.
`meuElementoLindo.addEventListener('nome do evento', nomeDaFuncaoASerExecutada ou a própria função anônima)`
Exs:
```
meuElementoLindo.addEventListener('click', event => {
    console.log("Faça alguma coisa! Tudo que estiver aqui vai ser executado quando alguém clicar em meuElementoLindo")
})

meuElementoLindo.addEventListener('click', event => {
    console.log("Você pode usar o argumento event para acessar informações sobre este evento, mas ele é útil para acessar o elemento que disparou este evento, neste caso, o que foi clicado!")
    console.log(event.target)
})

# Usando uma função atribuida a uma constante
const funcaoLinda = function umaFuncaoLinda(event) {
    console.log("Essa função pode ser reutilizada, inclusive você pode colocar ela em outro arquivo, por exemplo")
    console.log(event.target)
}
meuElementoLindo.addEventListener('mouseover', umaFuncaoLinda)
```

Mais umas coisas [aqui](https://gist.github.com/amantheroot/5322f230c0efa8c505456f65195d7bce)