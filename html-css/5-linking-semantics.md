# Ligamento e semântica #


## Âncoras ##

Uma página em HTML normalmente possui âncoras, comumente chamados de
_links_, para outros documenos HTML ou outras seções do mesmo documento.
Para definir uma âncora no HTML, utilizamos a _tag_ `a` (_Anchor_). Veja:

```html
<a href="https://softcom.github.io/">Softcom EJ</a>
```

O exemplo acima utiliza uma URI (_Uniform Resource Identifier_) absoluta, ou
seja, você descreve o protocolo, origem e caminho para identificar outro
documento. No entanto, quando estamos trabalho com âncoras fornecidos por uma
mesma origem, ou seja, disponibilizados por um mesmo "servidor", você pode
utilizar URIs relativas. Suponha que você tenha dois arquivos, um chamado
`index.html` e outro chamado `contact.html`. Você pode referênciá-los em URIs
relativas como:

```html
<!-- Arquivo index.html -->
<a href="/contact.html">Contato</a>
```
```html
<!-- Arquivo contact.html -->
<a href="/">Página Inicial</a>
<a href="/index.html">Página Inicial</a>
```

Note que o nome `index.html` pode ser omitido.


## Citações ##

Em HTML, você pode definir uma citação direta de duas formas: uma
**citação curta**, escrita durante um parágrafo, ou uma **citação longa**,
escrita em seu próprio bloco de conteúdo.

Para demarcar uma citação curta, utiliza-se a _tag_ `q`. Para indicar a
referência da citação, utiliza-se o atributo `cite`, que recebe como valor uma
URI da referência. Veja um exemplo:

```html
<p>
  De acordo com o <em>website</em> da Mozilla,
  <q cite="https://www.mozilla.org/en-US/about/history/details/">
    Firefox 1.0 foi lançando em 2004 e se tornou um grande sucesso
  </q>
  .
</p>
```

Já para citações longas, que precisam de um bloco de conteúdo próprio, o HTML
disponibiliza a _tag_ `blockquote`. Para indicar a referência da citação, você
pode utilizar novamente o atributo `cite` com sua URI. Veja:

```html
<blockquote cite="https://mitpress.mit.edu/sicp/full-text/book/book.html">
  Programas devem ser escritos para pessoas lerem, e eventualmente para
  máquinas executarem.
</blockquote>
```

Já quando você utiliza uma citação indireta, você pode utilizar a _tag_ `cite`,
que deve conter algum nome ou identificação da referência. Veja um exemplo:

```html
<p>
  <cite>O Grito</cite> de Edward Munch. Pintado em 1893.
</p>
```


## Seções de conteúdo ##

Um documento HTML possui várias seções, tais como cabeçalhos, rodapés,
menus de navegação e o corpo de texto principal. Provavelmente sua primeira
ação seria demarcar cada uma dessas seções em vários elementos `div`s com
classes e identificadores próprios. Mesmo que o elemento esteja bem formatado
em termos visuais, como o elemento `div` não tem qualquer significado
implícito, podemos ter um problema para usuários que não possuem "visão", como
é o caso de usuários com deficiência visual ou até mesmo robôs leitores de
documentos (indexadores de conteúdo, Google, Bing, entre outros). Para
adicionar semântica as seções de conteúdo, o HTML disponibiliza várias _tags_
que serão vistas a seguir.

### Cabeçalhos e Rodapés ###

Os elementos `header` e `footer` representam, respectivamente, um cabeçalho
e um rodapé da seção ou artigo que seja ancestral a eles. Um `header` é
utilizado para introduzir o documento e fornecer alguma navegação e normalmente
inclui a identidade visual do documento, como uma logo; e um campo de busca
no _website_. Já um `footer` tipicamente contém informação sobre o autor
do _website_ ou seção, informações de _copyright_, entre outras. Veja:

```html
<body>
  <header>
    <h1>Softcom EJ</h1>
    <ol>
      <li><a href="/about.html">Sobre</a></li>
      <li><a href="/products.html">Produtos</a></li>
      <li><a href="/contact.html">Contato</a></li>
    </ol>
  </header>

  <div class="container">
    <div class="main">
      <div class="article">
        <h1>O que é a Softcom?</h1>
        <p>
          A <strong>Softcom</strong> é uma empresa júnior que atua no setor de
          tecnologia de informação fundada em 2016 e atualmente localizada no
          Departamento de Informática da Universidade Estadual de Maringá.
        </p>
        ...
      </div>
    </div>

    <div class="ads">
      <h2>Seja nosso parceiro!</h2>
      ...
    </div>
  </div>

  <footer>
    <div>
      <strong>Universidade Estadual de Maringá</strong><br/>
      Departamento de Informática, Sala 5<br/>
      Av. Colombo, 5790 - Vila Esperanca<br/>
      Maringá - Paraná, CEP: 87020-900<br/>
    </div>
    <div>
      Copyright © 2016 Softcom Empresa Júnior. Todos os direitos reservados.
    </div>
    <div>
      <a href="/map.html">Mapa do Site</a>
      —
      <a href="/legal.html">Política de Privacidade</a>
    </div>
  </footer>
</body>
```

### Endereços e Navegação ###

Informações de contato, tais como endereços físicos, contatos telefônicos ou
de e-mail, do autor do documento, seção ou _website_ devem ser exibidas em
uma _tag_ `address`. Já informações de navegação, como âncoras para outras
páginas do _website_ ou para outras seções do próprio documento, devem estar
incluídos em uma _tag_ `nav`. Veja o exemplo anterior com a utilização desses
elementos:

```html
<body>
  <header>
    <h1>Softcom EJ</h1>
    <nav>
      <ol>
        <li><a href="/about.html">Sobre</a></li>
        <li><a href="/products.html">Produtos</a></li>
        <li><a href="/contact.html">Contato</a></li>
      </ol>
    </nav>
  </header>

  <div class="container">
    <div class="main">
      <div class="article">
        <h1>O que é a Softcom?</h1>
        <p>
          A <strong>Softcom</strong> é uma empresa júnior que atua no setor de
          tecnologia de informação fundada em 2016 e atualmente localizada no
          Departamento de Informática da Universidade Estadual de Maringá.
        </p>
        ...
        <h1>Missão, visão e valores</h1>
        <p>
          Nossa <strong>missão</strong> é promover o espírito empreendedor nos
          universitários e integrá-los no mercado de trabalho. Prover soluções,
          auxílio tecnológicos e capacitações buscando inovação para os desafios do
          cotidiano da comunidade interna e externa.
        </p>
        ...
      </div>
    </div>

    <div class="ads">
      <h2>Seja nosso parceiro!</h2>
      ...
    </div>
  </div>

  <footer>
    <address>
      <strong>Universidade Estadual de Maringá</strong><br/>
      Departamento de Informática, Sala 5<br/>
      Av. Colombo, 5790 - Vila Esperanca<br/>
      Maringá - Paraná, CEP: 87020-900<br/>
    </address>
    <div>
      Copyright © 2016 Softcom Empresa Júnior. Todos os direitos reservados.
    </div>
    <nav>
      <a href="/map.html">Mapa do Site</a>
      —
      <a href="/legal.html">Política de Privacidade</a>
    </nav>
  </footer>
</body>
```

### Conteúdo principal, conteúdo secundário e corpo de texto ###

O conteúdo principal de um documento HTML pode ser demarcado com a _tag_
`main`. Por definição, um documento HTML pode conter somente um elemento `main`
em toda sua estrutura. Portanto, reserve-o para a área que consiste de conteúdo
diretamente relacionado ao tópico central do documento - excluindo,por
exemplo, conteúdo repetido entre vários documentos como menus de navegação
gerais, anúncios e outros conteúdos à parte.

De forma geral, conteúdos secundários ou à parte — como anúncios, comentários,
entre outros — devem ser colocados em uma _tag_ `aside`. Um `aside` pode fazer
parte de um `main` desde que ele esteja relacionado ao assunto do tópico
principal. Como uma listagem de conteúdo relacionados em outros documentos.

O corpo de texto de um documento pode ser declarado com a _tag_ `article`.
Perceba que o elemento `article` inicia _de facto_ o corpo do texto do
conteúdo. Geralmente é utilizado para indicar o texto de um artigo científico,
de uma entrada de _blog_ ou de uma notícia. Os títulos de um artigo são
identificados pelos elementos de cabeçalho (`h1`, `h2`, `h3`...). Seções de
conteúdo podem ser demarcadas com a _tag_ `section`, que normalmente possuem
um assunto em comum.

Veja o exemplo anterior com as novas marcações:

```html
<body>
  <header>
    <h1>Softcom EJ</h1>
    <nav>
      <ol>
        <li><a href="/about.html">Sobre</a></li>
        <li><a href="/products.html">Produtos</a></li>
        <li><a href="/contact.html">Contato</a></li>
      </ol>
    </nav>
  </header>

  <div class="container">
    <main>
      <article>
        <section>
          <h1>O que é a Softcom?</h1>
          <p>
            A <strong>Softcom</strong> é uma empresa júnior que atua no setor
            de tecnologia de informação fundada em 2016 e atualmente localizada
            no Departamento de Informática da Universidade Estadual de Maringá.
          </p>
          ...
        </section>
        <section>
          <h1>Missão, visão e valores</h1>
          <p>
            Nossa <strong>missão</strong> é promover o espírito empreendedor
            nos universitários e integrá-los no mercado de trabalho. Prover
            soluções, auxílio tecnológicos e capacitações buscando inovação
            para os desafios do cotidiano da comunidade interna e externa.
          </p>
          ...
        </section>
      </article>
    </main>
    <aside>
      <h2>Seja nosso parceiro!</h2>
      ...
    </aside>
  </div>

  <footer>
    <address>
      <strong>Universidade Estadual de Maringá</strong><br/>
      Departamento de Informática, Sala 5<br/>
      Av. Colombo, 5790 - Vila Esperanca<br/>
      Maringá - Paraná, CEP: 87020-900<br/>
    </address>
    <div>
      Copyright © 2016 Softcom Empresa Júnior. Todos os direitos reservados.
    </div>
    <nav>
      <a href="/map.html">Mapa do Site</a>
      —
      <a href="/legal.html">Política de Privacidade</a>
    </nav>
  </footer>
</body>
```


---

## Atividades ##
