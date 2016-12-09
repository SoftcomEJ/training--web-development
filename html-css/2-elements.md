# Elementos HTML

O HTML é composto de várias *tags* HTML, formalmente chamados de **Elementos
HTML**. Existem vários elementos HTML, cada um com uma semântica bem definida
para organizar a informação do documento.


## Cabeçalhos

Quando queremos informar que um trecho do texto é um cabeçalho do documento,
seção, etc; utilizamos as *tags heading* para sua marcação. Veja:

```html
<h1>Softcom JR</h1>
<h2>Sobre a organização</h2>
<h3>Serviços Oferecidos</h3>
<h2>Contato</h2>
```

As *tags heading* vão desde o `h1` até o `h6`, indicando ordem hierárquica:
sendo `h1` o título de maior nível hieráquico e `h6` o de menor nível
hieráquico. Utiliza-se o `h1` para o título do documento ou da página, `h2`
para subtítulos ou títulos de seções do documento, e assim por diante.


## Parágrafos

Quando exibimos corpo de texto na página, é recomendado utilizar a *tag*
**parágrafo** `p`. Veja:

```html
<h2>Sobre a organização</h2>
<p>
  A Softcom é uma empresa júnior que atua no setor de tecnologia de informação
  fundada em 2016 e atualmente localizada no Departamento de Informática da
  Universidade Estadual de Maringá.
</p>
<h3>Serviços Oferecidos</h3>
<p>
  Oferecemos projetos de desenvolvimento de sistemas para a Web e Mobile.
</p>
```

Note que quebras de linhas em nosso texto não refletem em quebras de linha
na página exibida ao usuário. Quebras de linha se tornam espaços quando
renderizados, múltiplos espaços também são renderizados como um só espaço. Caso
você queira quebrar a linha de um parágrafo, use a tag `<br/>`.



## Mudança de ênfase

Mudanças de ênfase no texto podem ser feitas com diversas *tags*. Veja:

* A *tag* `strong` deixa um trecho "mais forte" — renderizado por padrão como
  negrito — normalmente indicando um trecho de importância ao contexto do
  documento;
* A *tag* `em` indica um trecho com "ênfase" — renderizado por padrão com
  itálico — normalmente indicando um trecho com pronúncia diferenciada, como
  termos estrangeiros.
* A *tag* `small` indica um trecho com menor relevância — renderizado por
  padrão com uma fonte menor — normalmente indicando um comentário feito
  no documento;

Veja um exemplo:

```html
<h2>Sobre a organização</h2>
<p>
  A <strong>Softcom</strong> é uma empresa júnior que atua no setor de
  tecnologia de informação fundada em 2016 e atualmente localizada no
  Departamento de Informática da Universidade Estadual de Maringá.
</p>
<h3>Serviços Oferecidos</h3>
<p>
  Oferecemos projetos de desenvolvimento de sistemas para a <em>Web</em> e
  <em>Mobile</em>.
</p>
```


## Listas

Listas em HTML são criadas com duas tags com propriedades distintas. Uma lista
ordenada, ou seja, que contém uma ordem defina por índices, pode ser criada
com a tag `ol` e normalmente renderiza os itens com o índice a frente. Cada
item da lista deve ser definido com a tag `li`, veja:

```html
<ol>
  <li>Primeiro item;</li>
  <li>Segundo item;</li>
  <li>Terceiro e último item.</li>
</ol>
```

Listas sem ordenação definida podem ser criadas com a tag `ul` e são
normalmente renderizadas como tópicos. Cada item novamente deve ser definido
com um `li`. Veja:

```html
<ul>
  <li>Banana;</li>
  <li>Melão;</li>
  <li>Abacaxi;</li>
</ul>
```

## Imagens

Para adicionar imagens em nosso documento, utilizamos a *tag* `img`. É
obrigatório a utilização de dois atributos para que a imagem seja exibida:
`src` e `alt`. O atributo `src` indica o local da imagem, já o `alt` indica
um texto alternativo para a imagem caso ela não possa ser exibida. Veja:

```html
<h1>Softcom JR</h1>
<h2>Sobre a organização</h2>
<p>
  A <strong>Softcom</strong> é uma empresa júnior que atua no setor de
  tecnologia de informação fundada em 2016 e atualmente localizada no
  Departamento de Informática da Universidade Estadual de Maringá.
</p>
<p>
  <img src="images/softcom-logo.png" alt="Logo da SoftcomEJ" />
</p>
<h3>Serviços Oferecidos</h3>
<p>
  Oferecemos projetos de desenvolvimento de sistemas para a <em>Web</em> e
  <em>Mobile</em>.
</p>
```

Caso queremos adicionar uma legenda imagem, é necessário a utilização de outras
*tags* auxiliares: `figure` e a `figcaption`, que indicam respectivamente a
definição de uma figura e de uma legenda. Veja:

```html
<figure>
  <img src="images/softcom-logo.png" alt="Logo da SoftcomEJ" />
  <figcaption>Logo da Softcom</figcaption>
</figure>
```

## Atividades

1. Copie a pasta "exercise-2" para o seu computador;
2. Crie um novo arquivo texto chamado "index.html";
3. Crie um documento HTML básico, como visto anteriormente, e abra-o no
   em um navegador da sua preferência;
4. Abra a imagem "template.png" e crie uma página HTML no documento
   "index.html" que siga o modelo proposto pela imagem:
   * No elemento `head`, crie a tag `<style></style>`, e copie o conteúdo
     do arquivo "styles.css" para o conteúdo dessa tag;
   * O conteúdo pode ser copiado do arquivo "content.txt";
