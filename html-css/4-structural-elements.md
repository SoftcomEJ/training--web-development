# Elementos estruturais

## Exibição de elementos

No HTML e CSS, há dois conceitos muito importantes para entender o mecanismo de
exibião de elementos na tela: os  **elementos de nível de linha**
(_Inline-level elements_) e os **elementos de nível de bloco** (_Block-level
elements_).

Elementos de nível de linha são aqueles elementos que não são apresentados como
novos blocos de conteúdo, mas sim distribuídos entre as linhas de um texto.
Alguns exemplos de elementos de nível de linha incluem as ênfases de texto
(`strong` e o `em`) e também as imagens (`img`).

Já um elemento de nível de bloco é um elemento que são formatados visualmente
na tela como um "bloco" e geralmente ocupa todo o espaço do elemento pai, que é
o seu limitante. Navegadores tipicamente exibem elementos de bloco em uma nova.
Alguns elementos de elementos de nível de bloco incluem o `p`, os elementos
cabeçalhos (`h1`, `h2`, `h3`...) e também as listas (`ol` e `ul`) e seus
itens (`li`).

Elementos de nível de linha não podem definir uma altura ou espaçamentos
verticais, pois estão sempre presos a altura da linha (`line-height`). No
entanto podem definir espaçamentos horizontais para distanciar-se dos texto ao
seu arredor. Enquanto elementos de nível de bloco são livres para definir uma
altura ou espaçamentos em qualquer direção, pois sempre iniciam um novo bloco
de conteúdo.


## Os elementos `div` e `span`

O HTML possui muitas _tags_ para os mais mais variados casos, tais como: `h1`
para títulos, `p` para parágrafos, `ol` para listas ordenadas, entre muitas
outras. Porém há casos onde não encontramos um elemento HTML que o descreva de
forma adequada, e nesses casos utilizamos os elementos `div` e `span`.

O elemento `div` é um elemento container genérico de conteúdo e que possui
exibição em nível de bloco. Ele não possui qualquer significado semântico,
somente sendo utilizado para "agrupar" outros elementos.

Já o elemento `span` é um container container genérico de texto e que possui
exibição em nível de linha. Assim como o `div`, não possui qualquer significado
semântico, sendo utilizado como um "agrupamento genérico" de texto.


## Identificando e selecionando elementos

Como você já deve ter percebido, a utilização de vários elementos iguais no
HTML, principalmente com a introdução das _tags_ `span` e `div`, torna a
criação de um arquivo CSS impossível de ser realizada a medida que a página
aumenta sua complexidade. Para resolver esse problema, o HTML e o CSS possuem
duas propriedades que nos permitem "selecionar" os elementos os quais queremos
aplicar estilos: os **identificadores** e as **classes**.

Os **identificadores** de elementos atuam como um "nome" único ao contexto da
página dado ao elemento. Para identificarmos um elemento, utilizamos o atributo
`id`. Veja:

``` html
<div id="card">
  <h2 id="card-header">Softcom EJ</h2>
  <div id="card-descriptor">
    Empresa Júnior de Computação e Informática locada na
    Universidade Estadual de Maringá.
  </div>
</div>
```

Agora que os elementos estão identificados, podemos aplicar regras de CSS
específicas para cada um deles. Para selecionar um elemento pelo atributo `id`,
utilizamos a sintaxe `#[identificador]`, como visto a seguir:

``` css
#card {
  background-color: #FFF;
}

#card-header {
  padding: 64px 8px 8px 8px;
  background-color: #3F51B5;
  font-size: 18px;
  font-family: sans-serif;
  color: #FFF;
}

#card-descriptor {
  padding: 8px;
  font-size: 14px;
  font-family: sans-serif;
  color: #777;
}
```

E terá um resultado parecido com:

<div style="background-color: #FFF; font-family: sans-serif; margin-bottom: 16px;">
  <h2 style="padding: 64px 8px 8px 8px; background-color: #3F51B5; font-size: 18px; color: #FFF;">Softcom EJ</h2>
  <div style="padding: 8px; font-size: 14px; color: #777;">
    Empresa Júnior de Computação e Informática locada na
    Universidade Estadual de Maringá.
  </div>
</div>

No entanto, um elemento só pode possuir um identificador e um identificador só
pode pertencer a um elemento. Mas e se tivessemos a necessidade de aplicar uma
regra de CSS em vários elementos de uma vez? Nesse caso, devemos utilizar as
**Classes**. Classes em HTML atuam como um rótulo que pode servir para
selecionar elementos no CSS e são declaradas no HTML pelo atributo `class`.
Veja:

``` html
<div id="card">
  <h2 id="card-header" class="font-sans text-white">Softcom EJ</h2>
  <div id="card-descriptor" class="font-sans">
    Empresa Júnior de Computação e Informática locada na
    Universidade Estadual de Maringá.
  </div>
</div>
```

Já no CSS, para selecionarmos elementos por meio de classes, utiliza-se a
sintaxe `.[nome da classe]`. Veja o exemplo anterior:

``` css
#card {
  background-color: #FFF;
}

#card-header {
  padding: 64px 8px 8px 8px;
  background-color: #3F51B5;
  font-size: 18px;
}

#card-descriptor {
  padding: 8px;
  font-size: 14px;
  color: #777;
}

.font-sans {
  font-family: sans-serif;
}

.text-white {
  color: #FFF;
}
```

Que terá um resultado similar a:

<div style="background-color: #FFF; font-family: sans-serif; margin-bottom: 16px;">
  <h2 style="padding: 64px 8px 8px 8px; background-color: #3F51B5; font-size: 18px; color: #FFF;">Softcom EJ</h2>
  <div style="padding: 8px; font-size: 14px; color: #777;">
    Empresa Júnior de Computação e Informática locada na
    Universidade Estadual de Maringá.
  </div>
</div>

Um elemento pode possuir quantas classes forem necessárias, basta adicioná-la
ao atributo `class`, separando-as por um espaço simples. Perceba que com
classes é possível reutilizar uma regra de CSS de várias formas em vários
elementos e, por isso, a utilização de classes é bastante poderosa.


## Definindo dimensões com CSS

Em CSS, você pode definir dimensões com duas propriedades:

  * `height`: para definir a altura do elemento;
  * `width`: para definir a largura do elemento;
  * `max-height` e `min-height`: definir a máxima e mínima altura de um
    elemento, respectivamente;
  * `max-width` e `min-width`: definir a máxima e mínima largura de um
    elemento, respectivamente;

Cada uma dessas propriedades aceita valores como medidas absolutas ou
porcentagens em relação a dimensão do elemento pai. Porém, definir o valor
de um elemento não significa que ele irá ter aquele valor. Isso acontece devido
o **Modelo de Caixa** do CSS.

O Modelo de Caixa do CSS é um modelo retangular de como cada elemento é
apresentado na interface do navegador. Veja na imagem abaixo:

<figure style="margin-bottom: 16px; text-align: center;">
  <img src="http://i.imgur.com/ULqumQ2.png" alt="Modelo de caixa do CSS" />
  <figcaption style="text-align: center;">
    Representação do Modelo de Caixa do CSS
  </figcaption>
</figure>

Por padrão, o dimensão de um elemento é calculado da soma dos valores de
`padding`, `border-width` e `width`. O valor de `margin` é adicionado também,
porém se duas margens se encontram, elas são "sobrepostas" uma sobre a outra.
Esse mecanismo é chamado colapso de margens.

Visto que esse é um mecanimos bastante complexo para a definição simples de
dimensão do elemento, normalmente utilizamos a propriedade `box-sizing` para
alterar a forma do cálculo de uma dimensão do CSS, que pode receber os valores:

  * `content-box`: valor padrão, a dimensão é calculada pelo conteúdo do
    elemento.
  * `border-box`: a dimensão é calculada a partir do limite da definição de
    borda, ou seja, se você definir um elemento com `width: 200px`,
    `padding: 20px` e `border-width: 2px`, o elemento continuará a ter `200px`;


## Posicionamento de elementos

O CSS também permite mudar o posicionamento de elementos na interface por meio
da propriedade `position`. Para estabelecer uma posição, você precisa inserir
uma coordenada. Essas coordenadas são comandadas pelas propriedades `top`,
`right`, `bottom` e `left`. Todos os valores da propriedade `position` só
trabalham com essas coordenadas.

### Posicionamento estático

O posicionamento estático é o posicionamento padrão e recebem o valor da
propriedade `position` como  `static`. Elementos com posicionamento estático
seguem o fluxo dado pela sua declaração no documento HTML e sempre reservam
o espaço do elemento.

<figure style="margin-bottom: 16px; text-align: center;">
  <img src="http://i.imgur.com/FHJrukT.gif" alt="Elemento com posicionamneto estático" />
  <figcaption style="text-align: center;">
    Um elemento posicionado estaticamente segue o fluxo de exibição do HTML.
  </figcaption>
</figure>

### Posicionamento fixo

O posicionamento fixo, definido quando a propriedade `position` recebe o valor
`fixed`, irá fixar a posição do elemento na coordenada que você definir a
partir do início da página, ou seja, o canto superior esquerdo da janela de
visão do navegador. A medida que a página é rolada, o elemento continua fixo na
posição que você definiu e o conteúdo da página rola normalmente. O
posicionamento fixo também não reserva espaço para o elemento, fazendo com que
outros elementos tomem seu lugar e que ele sobreponha-se a outros elementos.


<figure style="margin-bottom: 16px; text-align: center;">
  <img src="http://i.imgur.com/10lTptQ.gif" alt="Elemento com posicionamento fixo" />
  <figcaption style="text-align: center;">
    Um elemento posicionado fixamente permanece no mesmo local mesmo quando
    a página é rolada.
  </figcaption>
</figure>

### Posicionamento relativo

O posicionamento relativo é definido pela propriedade `position` com valor
`relative`. O posicionamento relativo possui um comportamento bastante similar
ao `static` por padrão, a diferença é que elementos com posicionamento relativo
podem receber valores `top`, `right`, `bottom` e `left`; a diferença é que ao
invés de utilizar o canto superior da página, o elemento posicionado
relativamente utiliza seu próprio canto superior direito para estabelecer a
referência da coordenada. O posicionamento relativo reserva o espaço ao
elemento.

<figure style="margin-bottom: 16px; text-align: center;">
  <img src="http://i.imgur.com/aGfEfq5.gif" alt="Elemento com posicionamento relativo" />
  <figcaption style="text-align: center;">
    Um elemento posicionado relativamente utiliza o seu próprio ponto inicial
    para referenciar as coordenadas.
  </figcaption>
</figure>

### Posicionamento absoluto

O posicionamento absoluto, definido com `position` com valor `absolute`,
funciona de maneira similar ao posicionamento relativo, porém utiliza o
elemento pai para calcular suas coordenadas. O posicionamento absoluto também
não reserva espaço para o elemento, fazendo com que outros elementos utilizem
o espaço antes ocupado por ele.

<figure style="margin-bottom: 16px; text-align: center;">
  <img src="http://i.imgur.com/nTy8UzO.gif" alt="Elemento com posicionamento absoluto" />
  <figcaption style="text-align: center;">
    Um elemento posicionado absolutamente utiliza o ponto superior esquerdo
    do elemento pai para referenciar as coordenadas.
  </figcaption>
</figure>

---

## Atividades

1. Copie a pasta `exercise-4` para o seu computador;
2. Abra o arquivo `index.html` no navegador e em um editor de texto;
4. Faça um cartão de visitas para você seguindo o modelo da imagem
   `template.png` utilizando os conceitos aprendidos nessa sessão.
    * Utilize a _tag_ `address` para criar o rodapé do cartão;
