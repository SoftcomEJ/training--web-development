# Tabelas #

Tabelas são formas uma forma comum de exibir dados tabulares em um documento.
No HTML, tabelas podem ser bastante simples ou bastante complexas, dependendo
da necessidade do desenvolvedor em expressar e estruturar a informação.

Toda tabela é iniciada pela _tag_ `table`. Porém, para exibir a informação
de forma tabular, precisamos definir uma linha de tabela e cada uma das suas
células. Cada linha em uma tabela é representada pelo elemento `tr`
(_Table Row_), enquanto uma célula pode ser representada como um cabeçalho,
com a _tag_ `th` (_Table Heading_) ou como uma célula de conteúdo utilizando a
_tag_ `td` (_Table Data_)

Uma tabela simples pode ser vista abaixo:

```html
<table>
  <tr>
    <th>Nome</th>
    <th>E-mail</th>
  </tr>
  <tr>
    <td>João Siqueira</td>
    <td>jsiqueira@exemplo.com</td>
  </tr>
  <tr>
    <td>Maria Verde</td>
    <td>maria.verde@email.com</td>
  </tr>
</table>
```

Nota-se que cada um dos campos da tabela estão alocados dentro de uma
_tag_ `th` ou `td` e a tabela é escrita linha por linha (_tag_ `tr`)

## Partes da tabela ##

É possível definir partes de uma tabela utilizando as _tags_ `thead`
(_Table Header_), `tbody` (_Table Body_) e `tfoot` (_Table Footer_).
Definir as partes de uma tabela facilita a estilização da mesma além de que
alguns navegadores permitem a rolagem do corpo da tabela, mantendo os conteúdos
de cabeçalho e rodapé sempre visiveis. Além de duplicar essas informações quando
solicitada a impressão de uma tabela em mais de uma página.

Um exemplo simples pode ser visualizado abaixo:
```html
<table>
  <caption>Venda de produtos de limpeza</caption>
  <thead>
    <tr>
      <th>Produto\Vendedor</th>
      <td>Jane</td>
      <td>Jadson</td>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Sabão</th>
      <td>100 un.</td>
      <td>50 un.</td>
    </tr>
    <tr>
      <th>Água Sanitária</th>
      <td>10 un.</td>
      <td>25 un.</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th>Total</th>
      <td>110 un.</td>
      <td>75 un.</td>
    </tr>
  </tfoot>
</table>
```
Nota-se que as _tags_ `thread`, `tbody` e `tfoot` por padrão não apresentam
nenhuma diferença visual para a tabela, somente informações semânticas.
A _tag_ `caption` indica somente uma legenda para a tabela.

## Agrupando células ##

É possível agrupar células com as propriedades `colspan` (colunas) e `rowspan`
(linhas). A utilização desses atributos se dá nas _tags_ `th` ou `td` com a
seguinte sintaxe:
```html
<td colspan="#"> ... </td>
<td rowspan="#"> ... </td>
```

Onde # indica a quantidade de células para agrupar

## Atividades ##
