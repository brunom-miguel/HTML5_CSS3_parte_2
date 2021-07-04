# HTML5_CSS3_parte_2
Segunda parte da formação Front-end da Alura.

* Já estava criado, na parte 1, a página inicial do projeto. Arquivo *index.html* e *style.css*

* Foi incluido a logo na tag **img** dentro da tag **h1**, pois a logo é o conteúdo mais importante da página,

* O arquivo reset.css reseta styles criados pelo próprio navegador.

### Posicionamento

* Posição *static*:
    * Parado no "modo padrão";
* Posição *relative*:
    * Está deslocado, e pode ser movimentado, mas o ponto inicial continua sendo o mesmo;
* Posição *absolute*:
    * Posicionamento absoluto em relação a outra coisa;
    * Muda o ponto inicial que o elemento se encontra;
    * Consigo posicionar meu elemento em qualquer lugar da página.
* Melhor técnica para alinhar uma **div** ao centro:
    * Usar cálculo da *margin* automático (auto);

### Tags semânticas

* Por que devemos usar as *tags semânticas* como o **<main>**?
    * Para deixar o código mais legível, tanto para nós, quanto para o navegador.
        * As tags semânticas fazem com que o navegador entenda melhor o conteúdo, e com isso carrega melhor a nossa página

### Itens de lista

* Quando temos uma lista de itens complexos, devemos utilizar a formatação abaixo:
```html
<li>
    <h2>Cabelo</h2>
    <img src="" alt="">
    <p>Descrição</p>
    <p>R$ 40,00</p>
</li>
```

### Inline-block

Em uma lista, colocamos a propriedade "display: inline block" no **ul**. O **ul** se comporta como um bloco, então usa 100% da largura da página.

* Como se comporta um elemento que tem seu **display** com o valor *inline-block*?
    * O tamanho pode ser ajustado, tanto na largura, quanto na altura

### Border-box

* Quando incluimos um espaçamento interno (padding), sendo que já contabilizamos os percentuais para fechar 100%, o navegador soma os pixels do padding + o percentual, assim temos uma quebra de bloco.
* Com **border-box** conseguimos definir uma largura fixa do elemento, e o navegador inclui os pixels (do padding) que incluimos DENTRO do percentual definido 