# HTML5_CSS3_parte_2

## Página: PRODUTOS 

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

## Página: CONTATO

### Formulários

Para decidir quando devemos usar um formulário nas nossas páginas, alguns motivos podem ser analisados:

1. Quando queremos enviar dados para um servidor;
2. Quando queremos capturar informações que o usuário digitar;
3. Quando queremos enviar os dados para uma outra página.

Um formulário pode servir para, entre outras coisas, enviar os dados para uma outra página, capturar informações que o usuário digitar e enviar os dados para um servidor.

#### Campo *form*

* Tag *input* com *type="text"* para incluir um campo de texto;
    * Junto com a tag *input* sempre inserimos a tag *label*
    * *input* geralmente é único, então incluimos um identificador (*id*);
    * Conecto o *label* e o *input* com um **id** e **for**:
        * ```HTML
            <label for="nome-sobrenome">Nome e Sobrenome</label>
            <input type="text" id="nome-sobrenome">
          ```
    * Usamos o *type="submit"*, para enviar o formulário para onde direcionarmos;
        * O valor do texto no botão será traduzido de *submit* para a língua usada no browser;
        * Para mudar o texto dentro do botão, colocamos o *value="novo texto"*:
            * ```HTML
                <input type="submit" value="Enviar formulário">
              ```
    * Para criar um campo de seleção usamos, na tag *input* o *type="radio"*, dessa forma selecionamos a opção desejada;
        * Também fazemos a ligação com uma tag *label* por meio do **id**;
        * No *name* colocamos os *inputs* que tem ligação, para que ao selecionar um, o outro seja desmarcado:
            * ```HTML
                <label for="radio-email">Email</label>
                <input type="radio" name="contato" value="email" id="radio-email">

                <label for="radio-telefone">Telefone</label>
                <input type="radio" name="contato" value="telefone" id="radio-telefone">

                <label for="radio-whatsapp">WhatsApp</label>
                <input type="radio" name="contato" value="whatsapp" id="radio-whatsapp">
          ```
        * Podemos criar o vínculo entre o *label* e o *input* incluindo, também, um dentro do outro, isso também inverte a posição da "bolinha" do **checkbox**/**radio**:
            * ```HTML
                <label for="radio-email">
                    <input type="radio" name="contato" value="email" id="radio-email">Email
                </label>
                
                <label for="radio-telefone">
                    <input type="radio" name="contato" value="telefone" id="radio-telefone">Telefone
                </label>

                <label for="radio-whatsapp">
                    <input type="radio" name="contato" value="whatsapp" id="radio-whatsapp">WhatsApp
                </label>
              ```
* Para incluir um campo de texto livre usamos a tag *textarea*
    * Por ser uma tag de conteúdo, ela tem a tag de fechamento:
        * ```HTML
            <textarea id="mensagem" cols="70" rows="10"></textarea>
        ```

###### Qual a melhor abordagem quando temos uma configuração CSS aplicada para um item e queremos replicar ela para um item parecido?

* Usar os seletores dos itens separados por vírgula:
    * ```CSS
        form label, form p {
        display: block;
        font-size: 20px;
        margin: 0 0 10px;
        }
      ```
* Criar uma classe:
    * ```CSS
        .input-padrao {
        display: block;
        margin: 0 0 20px;
        padding: 10px 25px;
        width: 50%;
        }
      ```

#### Select

* Com a tag *select*, criamos um seletor de opções, ao incluir o *option*:
    * ```HTML
        <select>
            <option>Manhã</option>
            <option>Tarde</option>
            <option>Noite</option>
        </select>
      ```

####  Hierarquia CSS

* Tag: 1
* Class: 10
* Id: 100
* Inline: 1000

#### Input para celulares

Melhorias de experiência para o usuário:

* Para texto:
    * ```HTML
        <input type="text">
      ```
        * Abre o teclado normal;
* Para email:
    * ```HTML
        <input type="email">
      ```
        * Abre o teclado normal, mas com algumas adaptações (inclusão do *@*, *.*, *.com*);
* Para telefone:
    * ```HTML
        <input type="tel">
      ```
        * Abre teclado númerico propício para telefone;
* Para inserir números:
    * ```HTML
        <input type="number">
      ```
        * Abre teclado na parte de números;
* Para inserir senhas:
    * ```HTML
        <input type="password">
      ```
        * Transforma os números digitados em *asteríscos* ou *bolinhas*;
* Para inserir data:
    * ```HTML
        <input type="date">
      ```
* Para inserir data e hora:
    * ```HTML
        <input type="datetime">
      ```
* Para inserir mês:
    * ```HTML
        <input type="month">
      ```
* Para inserir campo de busca:
    * ```HTML
        <input type="search">
      ```

#### Dados importantes no *input*

* *input* obrigatório:
    * Para tornar o campo do *input* obrigatório, basta incluir o **required** dentro:
        * ```HTML
            <input type="text" id="nome-sobrenome" class="input-padrao" required>
          ```
* Mensagem dentro do input:
    * Para colocar uma mensagem dentro do *input* explicando, basta incluir o **placeholder** dentro:
        * ```HTML
            <input type="email" id="email" class="input-padrao" placeholder="seuemail@dominio.com" required>
          ```
* Sugestão de marcação em botões *radio* ou *checkbox*:
    * Para deixar uma opção já marcada, como opção para o cliente, eu incluo o **checked** dentro do *input*:
        * ```HTML
            <input type="radio" name="contato" value="whatsapp" id="radio-whatsapp" checked>
          ```
#### Melhorando a semântica do formulário

* Em um formulário (dentro das tags *form*), para agrupar elementos do *form* que são relacionados, usamos a tag *fieldset*, ao invés da tag *div*. Além disso, para dar um título à seleção, usamos a tag *legend*, ao invés da tag *p*;
    * Sendo assim, ao invés de fazer assim:
        * ```HTML
            <form>
                <div>
                    <p>Qual horário prefere ser atendido?</p>
                    <select>
                        <option>Manhã</option>
                        <option>Tarde</option>
                        <option>Noite</option>
                    </select>
                </div>
            </form>
          ```
    * Fazemos assim:
        * ```HTML
            <form>
                <fieldset>
                    <legend>Qual horário prefere ser atendido?</legend>
                    <select>
                        <option>Manhã</option>
                        <option>Tarde</option>
                        <option>Noite</option>
                    </select>
                </fieldset>
            </form>
          ```

#### Transições

* No CSS3, para fazermos transições de cor, por exemplo, usamos a propriedade *transition* e informamos o tempo que queremos que a transição leve e o que será alterado:
    * ```CSS
        .enviar {
            transition: 0.5s background;
        }
        .enviar:hover {
            background-color: darkorange;
        }
      ```
    * Podemos definir que a transição ocorrerá para **todos** os elementos mudando o *background* para *all*:
        * ```CSS
            .enviar {
                transition: 0.5s all;
            }
            .enviar:hover {
                background-color: darkorange;
            }
          ```
#### Transformações

* No CSS3, para fazermos transformações no elemento que queremos, ao estar com o cursor em cima, por exemplo, usamos a propriedade *transform*;
    * Com o *transform* podemos aumentar o tamanho de todas as medidas do elemento proporcionalmente sem termos que fazer cálculos, usando o *scale()*;
        * Para aumentar em 20% o tamanho do botão de enviar, ao passar com o mouse por cima, por exemplo, ficará da seguinte forma:
            * ```CSS
                .enviar:hover {
                    background-color: darkorange;
                    transform: scale(1.2); /*importante usarmos o scale e ao invés de usar percentual (%) usamos a ideia de multiplicaçao (nesse caso, por 1.2)*/ 
                }
              ```
    * Com o *transform* podemos também girar o elemento ao passar com o mouse por cima, usando o *rotate()*:
        * Para girar em 70º usamos:
            * ```CSS
                .enviar:hover {
                    background-color: darkorange;
                    transform: scale(1.2); /*importante usarmos o scale e ao invés de usar percentual (%) usamos a ideia de multiplicaçao (nesse caso, por 1.2)*/ 
                    transform: rotate(70deg); /*gira o elemento em quantos graus eu quiser (deg = degree = grau)*/
                }
              ```
            * No entanto, se fizermos da forma acima, o tamanho (do *scale()*) não será mais realizado, pois a propriedade é a mesma e a de baixo *rotate()* sobrescreve a de cima *scale()*. Para solucionar isso, fazemos da seguinte forma:
                * ```CSS
                    .enviar:hover {
                        background-color: darkorange;
                        transform: rotate(70deg) scale(1.2);
                    }
                ```
#### Tabelas

* Tabelas são conjuntos de linhas e colunas. Para criar uma tabela no HTML começamos com a tag *table*. Cada linha é definida pela tag *tr* (table row) e dentro de cada linha colocamos as divisórias (colunas) com a tag *td* (table division)
* Para que a tabela seja semântica, usamos tags para definir o que é o cabeçalho, o que é o corpo e o que é o rodapé da tabela;
    * Para isso usamos as tags:
        * *thead* para **cabeçalho**;
            * Para as divisões (células) dentro do cabeçalho, usamos a tag *th* ao invés da *tr*:
                * ```HTML
                    <thead>
                        <tr>
                            <th>Dia</th>
                            <th>Horário</th>
                        </tr>
                    </thead>
                  ```
        * *tbody* para o **corpo**;
        * *tfoot* para o **rodapé**.
    * As tabelas também nos oferecem a possibilidade de juntar células, quando uma linha, que deveria ter 5 células, passa a mostrar só "uma célula". Esse efeito é conseguido através da propriedade *colspan=X*, onde X é o número de células que você quer agrupar:
        * ```HTML
            <tr>
                <td colspan="2" class="cidade-tabela">Porto Alegre</td>
            </tr>
          ```

## Página: HOME

#### Section

* Quando temos um conteúdo que corresponde ao mesmo objetivo, falam da mesma coisa e tem o mesmo fim, usamos a tag *section*.

* Diferença de *div* e *section*:
    * *div* : é uma divisão visual;
    * *section* : é uma divisão onde tem um conteúdo complexo;
        * Semanticamente as coisas fazem sentido (titulo e texto para a mesma coisa);
    * Exemplo:
        * ```HTML
            <section class="beneficios">
                <h3 class="titulo-centralizado">Benefícios</h3>

                <ul class="lista-beneficios">
                    <li class="itens">Atendimento aos clientes</li>
                    <li class="itens">Espaço diferenciado</li>
                    <li class="itens">Localização</li>
                    <li class="itens">Profissionais qualificados</li>
                </ul>
                <img class="imagem-beneficios" src="beneficios.jpg" alt="imagem beneficios">
            </section>
          ```
        * No exemplo acima temos um titulo (*h3*), uma lista (*ul*/*li*) e uma imagem (*img*). Todos para o mesmo assunto, mesmo objetivo.
    * Em geral, para um bloco onde o conteúdo tenha o mesmo significado, mesmo sentido, usamos uma *section*.

#### Medidas proporcionais com CSS

* px = píxels;
* % = percentual (já é uma medida proporcional);
* em = medida proporcional para *píxels*;

* Se quisermos que o tamanho da fonte do título, por exemplo, seja maior que o tamanho padrão da fonte, usamos a medida *em*:
    * Exemplo:
        * ```CSS
            .fonte-padrão {
                font-size: 15px;
            }
            .fonte-titulo {
                font-size: 2em; /* corresponde ao dobro do tamanho da fonte padrão, não importa qual seja seu tamanho (nesse caso, será 30px*/
            }
          ```

É importante usarmos um *espaçamento* que seja proporcional ao tamanho da fonte. Nesse caso, podemos usar, também, as medidas proporcionais para delimitar esse espaçamento:

```CSS
    .fonte-padrão {
        font-size: 15px;
    }
    .fonte-titulo {
        font-size: 2em;
        margin: 0 0 1em; /* espaço para baixo igual ao tamanho da própria fonte (que no caso, é 2x o tamanho da fonte padrão) */
    }
```