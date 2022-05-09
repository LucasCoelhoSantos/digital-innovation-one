# Introdução a criação de websites com HTML5 e CSS3 (Lucas Vilaboim)

## Estrutura básica

### Definição

> HTML = HyperText Markup Language (Linguagem de Marcação de Hipertexto)

HTML foi criado em 1991 por Tim Berners-Lee para melhorar a comunicação entre ele e seus colegas de trabalho no CERN. Seu processo de desenvolvimento gerou 4 outras versões: HTML2 (1995), HTML3 (1997), HMTL4 (1997), HTML5 (2014).

### Elemento HTML

Um elemento HTML é formado pela tag de abertura e seus atributos, o conteúdo e uma tag de fechamento (alguns elementos não possuem tag de fechamento).

![Anatomia de um elemento HTML](https://mdn.mozillademos.org/files/14717/mdn_Anatomia_de_um_elemento_HTML.png)

### Estrutura básica de um arquivo HTML

```HTML
<!doctype html>
<html>
    <head>
        <meta>
        <title></title>
    </head>
    <body>
    </body>
</html>
```

- `<html>` é a tag raíz do documento, todos os elementos HTML devem estar dentro dela.
- `<head>` é a tag que contém elementos que serão lidos pelo navegador, como os metadados.
- `<body>` é a tag que colocamos todo o conteúdo visível ao usuário: textos, imagens, vídeos.

## Semântica

Durante muitos anos o elemento padrão no HTML era a div, construíamos nosso conteúdo todo baseado nela, e assim nascia a sopa de divs.

Mas em 2014 saiu a quinta versão do HTML, e com ela vieram várias mudanças importantes, como performance e acessibilidade.

A semântica nos permite descrever mais precisamente o nosso conteúdo, agora um bloco de texto não é apenas uma div, agora é um article e tem mais significado assim.

|Tag        |Significado                                                                        |
|:---------:|:----------------------------------------------------------------------------------|
|`<section>`|Representa uma seção genérica de conteúdos (ex.: lista de artigos).                |
|`<header>` |Cabeçalho da página ou de parte da página (ex.: header de uma section).            |
|`<article>`|Representa um conteúdo relevante dentro da página (ex.: arigo de um blog).         |
|`<aside>`  |Representa um conteúdo relacionado ao conteúdo da página (ex.: links relacionados).|
|`<footer>` |Rodapé da página ou de parte da página (ex.: footer de um article).                |
|`<h1>-<h6>`|Títulos, havendo apenas um h1 por página.                                          |
|`<p>`      |Conteúdo do artigo.                                                                |
|`<a>`      |Âncora, interliga vários conteúdos na web.                                         |
|`<img>`    |Representa uma imagem.                                                             |

### Tags para textos

- `<h1>` Título da página `</h1>`
- `<h2>` Título de seção `</h2>`
- `<h3>` Título de artigo `</h3>`
- `<p>` Conteúdo do artigo `</p>`

### Tags para links

A tag `<a>` possui vários atributos, dentre eles:

- href: hyperlink para onde a âncora esta apontando, podendo ser uma página no site, link esterno, emails (mailto) ou telefones (tel).
- target: indica como o link vai ser aberto (_blank abre o link em uma nova aba).

### Tag img

A tag `<img>` não possui tag de fechamento e contém dois atributos:

- scr: é obrigatório e guarda o caminho da imagem.
- alt: é opcional e mostra a descrição da foto quando não carregada.

> Site de compressão de fotos [TinyPNG](https://tinypng.com/).

### Tags li, ul e ol

Listas servem para agrupar coleção de itens.

Na tag `<ul>` a ordem dos itens não importa.
Na tag `<ol>` a ordem dos itens é importante.
A tag `<li>` representa um item da lista.

## Introdução ao CSS3

Após a criação do HTML a necessidade de formatar as páginas ficou evidente, assim, em 1996, foi criada a linguagem de estilo que conhecemos por CSS.

A sintaxe é bem simples e pode ser explicada com a frase "você cria regras de estilo para elementos ou grupos de elementos".

Exemplo:

```CSS
/*seletores*/
a, p, h1, h3 {
    /*declarações*/
    color: blue;
    font-size: 14px;
}
```

Uma regra CSS é representada por um seletor ou um grupo de seletores separados por vírgula, então dentro de um par de chaves adicionamos as declarações, o exemplo acima está alterando a cor e o tamanho da fonte dos seletores, as declarações são formadas por uma propriedade e um valor.

Pseudo-classe: elementos HTML que sofrem alterações causadas pela interação do usuário, como mover o mouse por cima ou clicar nesse elemento.

### ID x Classe

No exemplo anterior a regra altera um elemento HTML diretamente, mas isso significa que todos os seletores informados ficarão com aquela aparência, e normalmente existem sites mais complexos que precisam de várias regras diferentes para elementos iguais.

O seletor do primeiro exemplo é um seletor de tipo, pois ele representa um elemento HTML, e com IDs e Classes podemos representar qualquer tipo de elemento mas há algumas diferenças entre eles:

- ID: é representado pelo símbolo # (hash) seguido de um nome para esse ID e só pode ser usado uma vez em uma página HTML.
- Classe: a classe é representada de forma parecida do ID, mas é precedida por um ponto em vez do hash e não possui restrição de uso.

## Conceitos básicos

### Box-model

![Box-model](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwww.lilengine.co%2Fsites%2Fdefault%2Ffiles%2Finline-images%2FScreen%2520Shot%25202019-04-14%2520at%252023.59.07.png&f=1&nofb=1)

Quando estamos criando o layout de um site o navegador representa cada elemento HTML  como uma caixa retangular, isso é o box-model. E com CSS nós alteramos a aparência dessa caixa (largura, altura, cor de fundo, etc.). Essa caixa é composta por 4 áreas: o conteúdo, o padding, a borda e a margem.

- As margens (margin) são espaçamentos entre elementos;
- As bordas (border);
- O padding é um espaçamento entre as bordas e o conteúdo, a diferença para as margens é que declarações de imagem de fundo funcionam nele;
- O conteúdo (content) é o que o seu bloco representa, um texto, uma imagem, um vídeo.

## Estilizando elementos

### Padding e Margin

É possível usar o padding com apenas um valor ou atribuir tamanhos diferentes para cada lado do box, algumas formas de fazer isso:

- Colocando um valor para as partes superior e inferior (eixo Y) e depois para os lados esquerdo e direito (eixo X).

    ```CSS
    .post {
        padding: 10px 5px;
    }
    ```

- Dando valores para cada lado do box.

    ```CSS
    .post {
        /*padding: 15px 10px 5px 0;*/
        padding-top: 15px;
        padding-right: 10px;
        padding-bottom: 5px;
        padding-left: 0;
    }
    ```

> Quando o valor for 0 não é preciso colocar a unidade de medida.

### Background

> [MDN Background](https://developer.mozilla.org/en-US/docs/Web/CSS/background)

Algumas das formas de colocar uma cor de fundo:

- pelo nome da cor em inglês;
- pelo código hexadecimal;
- usando apenas o atalho background.

```CSS
.post {
    background-color: green;
    background-color: #008800;
    background: #008800;
}
```

### Border

A propriedade border pode ter 3 valores:

- A largura que pode ser usada com várias unidades, como px, em e mm;
- A cor pode que ser atribuída pelo nome ou por um código hexadecimal, assim como o background;
- O estilo que é representado por palavras-chave:
  - solid: mostra uma borda simples e reta;
  - dotted: são bolinhas com um pequeno espaçamento entre elas;
  - dashed: forma uma linha tracejada.
- O border-radius permite arredondar os cantos de um elemento.

```CSS
.post {
    border: 3px solid blue;
    border-top: 2px dotted green;
    border-right: 4px dashed pink;
}
```

Propriedades específicas para cada aspecto de uma borda:

```CSS
/*atalho*/
.post {
    border: 3px solid #505050;
}
/*propriedades específicas*/
.post {
    border-width: 3px;
    border-color: #505050;
    border-style: solid;
}
```

> Com border-radius podemos usar várias unidades, mas as mais comuns são os pixels e a porcentagem e assim como no padding e margin, é possível mudar todos os cantos do elemento ou alterar cada canto separadamente.

## Estilizando textos

|Propriedade    |Significado                               |Observação                                               |
|:-------------:|:----------------------------------------:|:-------------------------------------------------------:|
|font-family    |Altera a fonte dos textos                 |Caso a primeira fonte não funcione, a segunda será usada |
|font-size      |Altera o tamanho do texto                 |Existem algumas unidades de medida                       |
|font-style     |Torna o texto itálico ou vice-versa       |Verificar se a fonte tem suporte ao itálico antes de usar|
|font-weight    |Altera o peso do texto                    |-                                                        |
|text-transform |Altera o texto entre maiúsculo e minúsculo|-                                                        |
|text-decoration|Usado para dar destaque em algum texto    |-                                                        |

Exemplo:

```CSS
#title {
    font-family: Verdana;
    font-size: 30px;
    font-weight: normal;
    text-transform: uppercase;
    text-decoration: underline;
}

.subtitle {
    text-transform: lowercase;
    text-decoration: overline;
}

.post_title {
    font-family: Verdana, Arial;
    font-size: 18px;
    font-weight: bold;
    /*primeiras letras de cada palavra em maísculo*/
    text-transform: capitalize;
    text-decoration: line-through;
}
```

> Com o font-family é possível alterar a fonte dos textos, com uma fonte da internet ou uma que esteja instalada no nosso computador, mas é recomendado usar fontes seguras, chamadas de web safe fonts (fontes encontradas em quase todos os sistemas e podem ser usadas sem preocupação).

## Estilizando listas

- list-style-type: altera o simbólo dos marcadores da lista.
- list-style-image: usa imagens como marcadores da lista.

```CSS
ul {
    list-style-type: square;
}

ol {
    list-style-type: upper-roman;
}

ul {
    list-style-type: "\1F44D";
}

ul {
    list-style-image: url("rocket.png");
}
```

## Propriedades de dimensões e alinhamento

|Propriedades|Significado                                                                                  |
|:----------:|:-------------------------------------------------------------------------------------------:|
|width       |Usado para ajustar a largura                                                                 |
|height      |Usado para ajustar a altura                                                                  |
|max-width   |Define a largura máxima que um elemento pode ter                                             |
|max-height  |Define a altura máxima que um elemento pode ter                                              |
|margin      |Usado para colocar espacamento entre elementos (valor auto alinha o elemento automáticamente)|
|text-align  |Usado para alinhar textos a esquerda, a direita, centralizar ou justificar                   |
