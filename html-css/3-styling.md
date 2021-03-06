# Personalizando o HTML

## Introdução ao CSS

Quando marcamos a informação com o HTML, adicionamos significado ao texto
exibido. Ou seja, trazemos **semântica** ao texto. O navegador estabelece
algumas modificações simples na aparência do texto: um `h1` fica maior e em
negrito, os parágrafos são espacaços entre si, e assim por diante. No entanto,
caso queiramos fazer páginas HTML com um design bonito e moderno, precisamos
personalizar cada um desses elementos.

Para isso, utilizamos outra linguagem, o **CSS** (_Cascading Style Sheets_),
que tem como objetivo somente definir regras de estilo para serem aplicadas
nos elementos. A vantagem é que o CSS é bem mais robusto que o HTML para
estilização, como veremos. Mas, principalmente, escrever formatação visual
misturado com conteúdo de texto no HTML se mostrou algo bem impraticável, por
exemplo, suponha que adicionamos estilo `in-line` para cada elemento HTML, e
no decorrer do projeto, decidimos mudar o estilo dos parágrafos. Nesse caso,
seria necessário percorrer todos os arquivos HTML, identificar as tags de
parágrafo (`<p>`) e modificá-las. Colocando essas regras de estilo em um
arquivo separado, temos apenas um ponto de alteração, facilitando a
manutenibilidade. O CSS resolve isso separando as coisas; regras de estilo não
aparecem mais no HTML, apenas no CSS.


## Sintaxe do CSS

De forma geral, o CSS é especificado com a sintaxe `[propriedade]: [valor];`.
Onde `[propriedade]` são regras definidas pela especificação do CSS
`[valor]` são valores válidos para a propriedade.


## Adicionando CSS ao HTML

Há três formas de adicionar estilos definidos com CSS em um documento HTML.

### Atributo `style`

Todo elemento HTML possui o atributo `style`, com ele é possível definir regras
CSS que serão aplicadas somente ao elemento e seus descendentes. Veja:

```html
<p style="color: pink; background-color: blue;">
  Esse conteúdo será exibido com fonte rosa em um fundo azul!
</p>
```

Mas tínhamos acabado de discutir que uma das grandes vantagens do CSS era
manter as regras de estilo fora do HTML. Usando o atributo `style` não fizemos
isso. Justamente por isso não se recomenda esse tipo de uso na prática, com
exceção de pequenos detalhes.


### A _tag_ `style`

A outra maneira de se utilizar o CSS é declarando suas propriedades dentro de
uma _tag_ `style`. Porém, para declarar uma regra de estilo, precisamos primeiro
selecionar um elemento que irá receber essas _tags_. Para isso, utilizamos os
**seletores CSS**, que indicam quais elementos do documento irão receber
o estilo definido. No exemplo abaixo, o seletor CSS seleciona todas as _tags_
`p` e aplica um estilo a elas.

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Softcom</title>
    <style>
      p {
        background-color: blue;
        color: pink;
      }
    </style>
  </head>
  <body>
    <p>
      O conteúdo será exibido em rosa com fundo azul
    </p>
    <p>
      <strong>Também</strong> será exibido em rosa com fundo azul
    </p>
  </body>
</html>
```

Os estilos definidos na _tag_ `style` são aplicados a todo o documento HTML.

### Arquivo externo

A terceira maneira de declararmos os estilos do nosso documento é com um
arquivo externo, geralmente com a extensão `.css`. Para que seja possível
declarar nosso CSS em um arquivo à parte, precisamos indicar em nosso documento
HTML uma ligação entre ele e a folha de estilo. Para isso, utilizamos uma _tag_
especial chamada `link`, indicando no atributo `rel` (relation) que será um
documento de declaração de estilos e no atributo `href` o local do arquivo CSS.

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Softcom</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <p>
      O conteúdo será exibido em rosa com fundo azul
    </p>
    <p>
      <strong>Também</strong> será exibido em rosa com fundo azul
    </p>
  </body>
</html>
```

No arquivo `styles.css`, vocẽ coloca apenas:

``` css
p {
  background-color: blue;
  color: pink;
}
```


## Algumas propriedades do CSS

Vimos que a propriedade `color` altera a cor do texto de um elemento HTML,
enquanto a propriedade `background-color` altera a cor do fundo desse elemento.
No entanto, muitas outras propriedades existe em CSS. Veremos as mais
utilizadas nessa seção.

### Fonte de texto

Algumas das principais propriedades para alterar a fonte do texto:

  * `font-family`: Altera a família de fonte exibida pelo elemento, tal como
    "Arial", "Comic Sans", "Times New Roman", entre outras. Pode-se também
    requisitar que a fonte seja exibida de forma genérica, como `sans-serif`
    (Uma fonte sem serifa), `serif` (Uma fonte com serifa) ou `monospace`,
    que apresenta largura igual em todos os caracteres. Pode-se definir
    várias fontes na propriedade `font-family`, que serão mostradas ao
    usuário como um "respaldo" caso a fonte anterior não seja encontrada;

  * `font-weight`: Altera o "peso" da fonte, ou seja, se a fonte é negrito,
    normal ou leve. Aceita `light`, `normal`, `bold`, entre outros;

  * `font-style`: Indica se a fonte possui alguma estilização própria, como
    itálico ou se é oblíqua. Aceita valores `italic`, `normal` e `oblique`;

![Exemplos da aplicação de propriedades de personalização de fontes.](http://i.imgur.com/Le7GVhd.png)


### Alinhamento de texto

A disposição do texto pode ser alterada com as seguintes propriedades:

  * `text-align`:  altera o alinhamento do texto. Aceita valores `left`
    (esquerda), `right` (direita), `center` (centralizado), `justify`
    (justificado), entre outros;

  * `text-indent`: altera o tamanho da distância recuo de primeira linha do
    paragráfo. Recebe valores de medida de tamanho, tais como (`32px`, `1cm`,
    `2in`, etc.);

  * `line-height`: altera o tamanho da distância entre as linhas. Recebe um
    valor de medida de tamanho.

![Exemplos da aplicação de propriedades de personalização de texto.](http://i.imgur.com/g3QyICp.png)


### Fundo

O fundo de um elemento pode ser alterado com as propriedades:

  * `background-color`: Altera a cor do fundo do elemento. Recebe como
    valor uma cor ou `transparent`.

  * `background-image`: Adiciona um elemento de imagem ao fundo do elemento.
    Recebe valores como `url('[caminho]')`, `none`, um gradiente, entre outras
    definições.

  * `background-repeat`: Repetir a imagem horizontalmente ou verticalmente.
    Recebe os valores `no-repeat`, `repeat-x`, `repeat-y`.

  * `background-position`: Posicionar o início da imagem de fundo no elemento,
    aceita dois valores que indicam o comportamento na horizontal e na
    vertical. Pode receber:
      - Posições (`top`, `right`, `bottom`, `left`, `center`);
      - Medida em relação a origem;
      - Porcentagens de posição.

  * `background-size`: Indica o tamanho do fundo, pode receber os valores:
      - Porcentagens em relação ao original;
      - Medida absoluta;
      - `contain`, redimensiona o fundo para conter-se ao elemento;
      - `cover`, redimensiona o fundo para cobrir o elemento.

![Exemplos da aplicação de propriedades de personalização de fundo.](http://i.imgur.com/Wu8uf2b.png)


### Bordas

Bordas de um elemento podem ser adicionadas com as propriedades:

  * `border-width`: O tamanho da espessura da borda;
  * `border-color`: A cor da borda;
  * `border-style`: O estilo da borda, pode receber valores como `solid`,
    `dotted`, `dashed`, `double`, entre outros.

![Exemplos da aplicação de propriedades de personalização de borda.](http://i.imgur.com/RLGlY5a.png)


### Espaçamento

Podemos definir espaçamentos internos ou externos. Para espaçamentos internos,
ou seja, espaçamentos entre a borda e conteúdo, utilizamos a propriedade
`padding-[lado]`, que recebe um valor de tamanho indicando, onde `[lado]`
pode ser `top`, `right`, `bottom` e `left`.

Já espaçamentos externos, entre a borda do elemento e elementos externos, podem
ser definidos com a propriedade `margin-[lado]` e recebe também um tamanho.
`lado` pode ser, novamente, `top`, `right`, `bottom` e `left`.

![Exemplos da aplicação de propriedades de personalização de espaçamento.](http://i.imgur.com/7lknqyo.png)

As propriedades de espaçamento `margin` e `padding` possuem atalhos para
definir cada um valor para cada um dos lados. Como no exemplo abaixo:

``` css
p {
  margin: 10px 20px 16px 8px;
  padding: 1cm 1.2in;
}
```

Quando uma propriedade de espaçamento possui quatro valores, eles indicam o
valor de cada lado, a partir do topo, em um sentido horário. Nesse exemplo,
o valor de margem em `top`, 10 pixels; `right`, 20 pixels; `bottom`, 16 pixels
e `left`, 8 pixels. Agora, quando uma propriedade de espaçamento possui dois
valores, eles indicam os espaçamentos verticais e horizontais. Ou seja, nesse
exemplo, o valor de `padding` é de 1 centímetro em `top` e `bottom` e de 1,2
polegadas em `left` e `right`.


---

## Atividades

1. Copie a pasta `exercise-3` para o seu computador;
2. Abra o arquivo `template.png`;
3. Abra o arquivo `index.html` no seu navegador;
4. Abra o arquivo `styles.css` em um editor de texto;
5. Recrie a página proposta em `template.png` na página do documento
   `index.html` com as técnicas aprendidas até agora.
    * Você não deve alterar o arquivo `index.html`, somente o arquivo
      `styles.css`.
