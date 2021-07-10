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

##### Questão

* Qual o comportamento do elemento quando adicionamos espaçamento interno, o **padding**?
    * O elemento aumenta seu tamanho:
        * Quando declaro um espaçamento interno, estou ***aumentando*** o conteúdo.

### Borda

* Quando adiciono a declaração de borda abaixo, qual o comportamento esperado?
    * ```CSS
      border: 3px solid #000000;
      ```
    * Uma borda *sólida*, com *3 pixels de largura*, **entre** o *padding* e a *margin*.

##### Borda com canto arredondado

* Funcionalidade veio na versão 3 do CSS (CSS3)
    * Usamos a propriedade *border-radius* (raio da borda)

### Pseudo-classes de estado

##### *:hover*

* O *:hover* atua modificando o estado do elemento enquanto o usuário está com o mouse em cima.
    * ```CSS
        nav a:hover {
        color: #C76C16;
        text-decoration: underline;
        }
     ```
* Em **todos** os elementos do HTML conseguimos mapear o comportamento com CSS e alterar o visual do elemento;
    * Exemplo alterando a cor da borda de um **li**:
        * ```CSS
            .produtos li:hover {
                border-color: #C76C16;
             }
          ```
* Alteração de tamanho da fonte:
    * Para alterar o tamanho da fonte de um elemento (título, por exemplo), não basta apenas incluir dentro do *:hover*, pois o tamanho do título já está definido previamente.
        * ```CSS
            .produtos li:hover {
                    border-color: #C76C16;
                    font-size: 40px;
            }
          ```
    * Para que a fonte seja alterada, preciso indicar que quero modificar o elemento do texto específico:
        * ```CSS
            .produtos li:hover h2 {
                font-size: 40px;
            }
          ```
        * Com o **.produtos li:hover** estou indicando que quero modificar o comportamento do *li*, mas não do *h2*. Para que o *h2* seja modificado, preciso indicar isso.
* Podemos usar o comportamento do *:hover* em um elemento quando:
    * Queremos realçar alguma característica quando o mouse do usuário estiver por cima do elemento;
        * No *:hover*, **mapeamos** o comportamento do mouse por cima do elemento, e podemos usar isso para destacar visualmente o elemento em questão.

##### *active*

* O *:active* atua modificando o estado do elemento enquanto o usuário está com o "clique" do mouse ativo no elemento.
    * ```CSS
        .produtos li:active {
            border-color: #088C19; 
        }
      ```

### Imagem no Background

* Adincionamos usando o valor *url* no *background* do elemento (no CSS):
    * No CSS referenciamos o endereço de uma imagem, usando o valor *url*.

### Unicode

* Site do [Unicode Table](https://unicode-table.com/en/)