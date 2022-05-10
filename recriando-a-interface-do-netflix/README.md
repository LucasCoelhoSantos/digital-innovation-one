# Recriando a Interface do Netflix (Felipe Aguiar)

## Descrição do Desafio

Recrie a interface do principal site de streaming mundial, [Netflix](https://www.netflix.com/br/), utilizando tecnologias simples como HTML5, CSS3 e JavaScript. Nesse projeto você aprenderá: como estruturar um layout, técnicas de CSS3 com containers e variáveis, como posicionar os elementos com Flexbox e como utilizar plugins JQuery a favor da sua aplicação.

> Dica: você pode dar um "fork" no repositório disponibilizado pelo expert para organizar melhor as suas alterações e evoluções, mantendo uma referência direta ao código original.

## Instalar

- Uma IDE ([Visual Studio Code](https://code.visualstudio.com/))
- Um navegador ([Chrome](https://www.google.com.br/chrome/))

### Extensões VSCode

- Live Server (ID: ritwickdey.LiveServer)
- Auto Rename Tag (ID: formulahendry.auto-rename-tag)
- Dracula Official (ID: dracula-theme.theme-dracula)

### Atalhos VSCode

- Alt + Shift + seta down (clona linha atual)

## Links Úteis

- Implementação de referência: [Repositório no GitHub](https://github.com/felipeAguiarCode/netflix-clone)
- Fontes externas para projeto: [Google Fonts](https://fonts.google.com/)
- Pesquisar informações de uma série: [The Movie Database](https://www.themoviedb.org/)
- Script de ícones em .SVG: [Font Awesome](https://fontawesome.com/)
- Biblioteca JS para criar carroséis: [Owl Carousel](https://owlcarousel2.github.io/OwlCarousel2/)

> OBS.: Focar nos elementos HTMl e o que irá ter dentro deles e na formatação, todo o resto, realizar na próxima etapa, a refatoração.

## Reset CSS

Cada navegador tem um valor padrão de padding e margin, por isso é recomendável resetar alguns valores (margin, padding, box-sizing) para evitar eventuais conflitos e erros.

```CSS
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

## Variáveis no CSS

Definir dentro da raíz do documento, ou seja, dentro do elemento root, geralmente usado para guardar cores padrões do projeto.

```CSS
:root {
    --vermelho: #E50914;
    --preto: #141414;
}
```

> Uma boa prática de programação é não utilizar caracteres acentuados em classes e nomes de variáveis.

## Elementos em caixa

- Wrapper = Envelopar

Caixa container ou Wrapper, utilizado para armazenar/envelopar um conjunto de informações (outras caixas pequenas), facilitando a movimentação dos movimentos movendo apenas a caixa maior (pode ser utilizado o vários Wrappers que serão alinhados da mesma maneira).

- Muitas coisas no CSS não tem uma propriedade ou código pronto, pois são alguns truques/técnicas.

![Ilustração Wrapper](https://scalablecss.com/static/2f8fd14811616e9884b4f42aa2b3009e/37523/bem-wrappers-1.png)

> Herança: No CSS, os elementos filhos diretos herdam as informações do elemento pai.

## jQuery

O jQuery é um framework/ferramenta que está chegando em seu fim, mas é utilizado em vários projetos e por isso é importante aprender ou conhecer o jQuery e alguns de seus plugins mais utilizados.

> Programar é resolver problemas, portanto não fique preso a uma tecnologia.
>
> Recomendável explorar o JS Vanilla em projetos novos ao invés de usar o jQuery.

### Utilizando Owl Carousel

Dentro de [Demos](https://owlcarousel2.github.io/OwlCarousel2/demos/demos.html) tem vários tipos de carousel responsivos.

Como implementar um carousel pelo JavaScript:

```javascript
// $ em javascript geralmente se remete ao jQuery.
$('.owl-carousel').owlCarousel({
    // navegação infinita
    loop:true,
    // margem entre um poster e outro
    margin:10,
    // botoes de navegação
    nav:true,
    // responsividade relacionada a quantidade de pixels
    responsive:{
        0:{
            items:1
        },
        600:{
            items:3
        },
        1000:{
            items:5
        }
    }
})
```

```html
<div class="owl-carousel owl-theme">
    <div class="item"><h4>1</h4></div>
    <div class="item"><h4>2</h4></div>
    <div class="item"><h4>3</h4></div>
</div>
```

## Responsividade (media queries)

Utilizar o inspecionar elemento (Ctrl + Shift + I) para entender/descobrir em que momento (pixels) aplicar a responsividade para cada tamanho de tela. Recurso também utilizado para testar os diferentes tamanhos de tela.

- O mais relevante é controlar o tamanho de um elemento toda vez que a tela tiver o tamanho proposto pela media querie.

## Desafios extras

- [] Dar vida aos botões em tela
- [] Fazer uma nova roupagem
- [] Fazer uma nova funcionalidade
