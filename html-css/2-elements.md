# Elementos HTML

O HTML é composto de várias _tags_, formalmente chamados de **Elementos
HTML**. Existem vários elementos HTML, cada um com uma semântica bem definida
para organizar a informação do documento.


## Cabeçalhos

Quando queremos informar que um trecho do texto é um cabeçalho do documento,
seção, etc; utilizamos as **_tags heading_** para sua marcação. Veja:

```html
<h1>Softcom JR</h1>
<h2>Sobre a organização</h2>
<h3>Serviços Oferecidos</h3>
<h2>Contato</h2>
```

As _tags heading_ vão desde o `h1` até o `h6`, indicando ordem hierárquica:
sendo `h1` o título de maior nível hieráquico e `h6` o de menor nível
hieráquico. Utiliza-se o `h1` para o título do documento ou da página, `h2`
para subtítulos ou títulos de seções do documento, e assim por diante.


## Parágrafos

Quando exibimos corpo de texto na página, é recomendado utilizar a _tags_
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
você queira quebrar a linha de um parágrafo, use a _tag_ `<br/>`.



## Mudança de ênfase

Mudanças de ênfase no texto podem ser feitas com diversas _tags_. Veja:

* A _tags_ `strong` deixa um trecho "mais forte" — renderizado por padrão como
  negrito — normalmente indicando um trecho de importância ao contexto do
  documento;
* A _tags_ `em` indica um trecho com "ênfase" — renderizado por padrão com
  itálico — normalmente indicando um trecho com pronúncia diferenciada, como
  termos estrangeiros.
* A _tags_ `small` indica um trecho com menor relevância — renderizado por
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

Listas em HTML são criadas com duas _tags_ com propriedades distintas. Uma lista
ordenada, ou seja, que contém uma ordem defina por índices, pode ser criada
com a _tag_ `ol` (ordered list) e normalmente renderiza os itens com o índice
a frente. Cada item da lista deve ser definido com a _tag_ `li` (list item),
 veja:

```html
<ol>
  <li>Primeiro item;</li>
  <li>Segundo item;</li>
  <li>Terceiro e último item.</li>
</ol>
```

Listas sem ordenação definida podem ser criadas com a _tag_ `ul` (unordered
list) e são normalmente renderizadas como tópicos. Cada item novamente deve ser
 definido com um `li`. Exemplo:

```html
<ul>
  <li>Banana;</li>
  <li>Melão;</li>
  <li>Abacaxi;</li>
</ul>
```

## Imagens

Para adicionar imagens em nosso documento, utilizamos a _tags_ `img`. É
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

Caso queremos adicionar uma legenda à imagem, é necessário a utilização de
outras _tags_ auxiliares: `figure` e a `figcaption`, que indicam respectivamente
 a definição de uma figura e de uma legenda. Veja:

```html
<figure>
  <img src="images/softcom-logo.png" alt="Logo da SoftcomEJ" />
  <figcaption>Logo da Softcom</figcaption>
</figure>
```

---

## Atividades

1. Copie a pasta `exercise-2` para o seu computador;
2. Crie um novo arquivo texto chamado "index.html";
3. Crie um documento HTML básico, como visto anteriormente, salve-o com o nome
   `index.html` e abra-o em um navegador de sua preferência;
4. No elemento `head`, adicione a seguinte _tag_:
   `<link rel="stylesheet" href="styles.css" />`;
4. Abra a imagem `template.png`;
5. No arquivo `index.html`, recrie a página dada pela imagem. O conteúdo pode
   ser copiado do arquivo "content.txt". Para ver o resultado do seu trabalho,
   atualize a página aberta no navegador com <kbd>F5</kbd>;
