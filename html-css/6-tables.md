# Tabelas #

Tabelas são formas uma forma comum de exibir dados tabulares em um documento.
No HTML, tabelas podem ser bastante simples ou bastante complexas, dependendo
da necessidade do desenvolvedor em expressar e estruturar a informação.

Toda tabela é iniciada pela _tag_ `table`. Porém, para exibir a informação
de forma tabular, precisamos definir uma linha de tabela e cada uma das suas
células. Cada linha em uma tabela é representada pelo elemento `tr`
(_Table Row_), enquanto uma célula pode ser representada como um cabeçalho,
com a _tag_ `th` (_Table Heading_) ou como uma célula de conteúdo

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

Nota-se que ccada
