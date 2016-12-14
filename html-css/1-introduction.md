# Introdução

A linguagem de marcação HTML (*HyperText Markup Language*) é uma linguagem
de marcação para a estruturação de documentos de hipertexto. O HTML, juntamente
com o CSS (*Cascading Style Sheets*) e o JavaScript, constituem a base
tecnológica da plataforma *Web*.

De forma bastante simples, podemos estabelecer a responsabilidade de cada
tecnologia como:

* **HTML**: Responsável por estruturar e manter a semântica da informação;
* **CSS**: Responsável por estilizar e alterar a aparência da informação;
* **JavaScript**: Responsável por adicionar dinâmica e interação à página Web.

Navegadores recebem documentos HTML de um servidor *Web* ou de algum caminho
local e então renderizam na tela uma página multimídia.


## Sintaxe

De forma geral, o HTML é escrito com um conjunto de *tags* responsáveis pela
marcação do conteúdo do documento. Uma *tag* pode ser escrita de duas formas:
com **abertura e fechamento** ou como **única**. Uma *tag* com **abertura e
fechamento**, tal como a `h1`, é escrita como escrita como `<h1></h1>`. Já
quando uma *tag* ela é **única**, tal como a `img`, é escrita como `<img/>`.

*Tags* podem possuir também **atributos** em sua definição, escritos com
sintaxe `nome="valor"`, como quando definimos uma entrada com o `input`,
`<input type="text" value=""/>`.


## Estrutura Básica

Um documento HTML básico precisa conter alguns elementos para que seja mostrado
na interface do navegador de forma correta, veja:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8"/>
    <title></title>
  </head>
  <body>
    <!-- Comentário -->
  </body>
</html>
```

Podemos ver que um documento bastante pequeno, mas vamos ver o que cada
componente significa:

  * A *tag* `<html></html>` indica que o documento HTML irá ser escrito,
    e possui duas *tags* filhas e irmãs, `head` e `body`.
  * A *tag* `head` contém informações que são do interesse do Navegador. As
    informações presentes na *tag* `head` não serão exibidas ao usuário que
    visualizar a página. A especificação do HTML obriga a definição de ao menos
    duas *tags* dentro do `head`, e são elas:
      - A *tag* `meta` é utilizada para definir **metainformações** do
        documento HTML. Uma dessas metainformações é a codificação dos
        caracteres utilizada pelo documento. É recomendado a utilização da
        codificação **UTF-8** por ser suportada na grande maioria dos
        navegadores e abranger uma grande variedade de idiomas do mundo;
      - A *tag* `title` define o título do documento HTML, que normalmente
        é exibido na barra de título da janela ou aba do navegador.
  * A *tag* `body` contém o corpo do documento. O que está contido dentro do
    `body` irá ser exibido pelo navegador ao usuário.
      - No corpo do `body` temos um comentário. Esse comentário não é
        levado em conta quando o navegador renderiza o documento para a
        exibição ao usuário. Comentários podem ser colocados em qualquer parte
        do documento.
  * A instrução `DOCTYPE`, definida no início do documento, não é uma *tag*
    HTML, mas uma instrução especial para indicar ao navegador a versão do HTML
    utilizada. No nosso exemplo estamos utilizando a versão mais recente do
    HTML, a versão 5.
