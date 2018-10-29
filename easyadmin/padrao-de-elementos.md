# Padrão de Elementos - Easy Admin

Este documento especifica padrões funcionais e visuais que deve ser empregados em telas do Easy Admin.

## Tópicos

1.  [Definições e Especificações de aplicação](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#defini%C3%A7%C3%B5es-e-especifica%C3%A7%C3%B5es-de-aplica%C3%A7%C3%A3o)
   1. [Conteúdos complementares](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#conte%C3%BAdos-complementares)
      1. [Definições de localização](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#defini%C3%A7%C3%B5es-de-localiza%C3%A7%C3%A3o)
      1. [Mensagens em modal de erro](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#mensagens-em-modal-de-erro)
      1. [Mensagens em modal de sucesso ou aviso complementares](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#mensagens-em-modal-de-sucesso-ou-aviso-complementares)
      1. [Menus de navegação lateral](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#menus-de-navega%C3%A7%C3%A3o-lateral)
      1. [Conteúdo complementar do módulo](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#conte%C3%BAdo-complementar-do-m%C3%B3dulo)
   1. [Recursos de formulário](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#recursos-de-formul%C3%A1rio)
      1. [Controle de texto com auto-complete de conteúdo (`input-search`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#controle-de-texto-com-auto-complete-de-conte%C3%BAdo-input-search)
      1. [Lista de seleção única (`select`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#lista-de-sele%C3%A7%C3%A3o-%C3%BAnica-select)
      1. [Lista de seleção múltipla (`tags`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#lista-de-sele%C3%A7%C3%A3o-m%C3%BAltipla-tags)
         1. [Com lista prévia de opções (`tags-search`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#com-lista-pr%C3%A9via-de-op%C3%A7%C3%B5es-tags-search)
         1. [Sem lista prévia de opções (`tags-live`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#sem-lista-pr%C3%A9via-de-op%C3%A7%C3%B5es-tags-live)
      1. [Lista de seleção múltipla em árvore (`tree-view`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#lista-de-sele%C3%A7%C3%A3o-m%C3%BAltipla-em-%C3%A1rvore-tree-view)
      1. [Seleção de valores boleano (`input-checkbox`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#sele%C3%A7%C3%A3o-de-valores-boleano-input-checkbox)
      1. [Seleção de valores boleano de status (`switch`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#sele%C3%A7%C3%A3o-de-valores-boleano-de-status-switch)
      1. [Seletores múltiplos de única opção (`input-radio`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#seletores-m%C3%BAltiplos-de-%C3%BAnica-op%C3%A7%C3%A3o-input-radio)
      1. [Ícones em controles de formulário](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#%C3%8Dcones-em-controles-de-formul%C3%A1rio)
      1. [Links em controles de formulário](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#links-em-controles-de-formul%C3%A1rio)
      1. [Textos de ajuda para preenchimento de campos (`control-help`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#textos-de-ajuda-para-preenchimento-de-campos-control-help)
      1. [Textos de informações complementares para preenchimento de campos (`control-tooltip`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#textos-de-informa%C3%A7%C3%B5es-complementares-para-preenchimento-de-campos-control-tooltip)
      1. [Apresentação de controle com erro de preenchimento (`has-error`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#apresenta%C3%A7%C3%A3o-de-controle-com-erro-de-preenchimento-has-error)
      1. [Apresentação de controle com warning de preenchimento (`has-warning`)](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#apresenta%C3%A7%C3%A3o-de-controle-com-warning-de-preenchimento-has-warning)
   1. [Ações de formulário](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#a%C3%A7%C3%B5es-de-formul%C3%A1rio)
      1. [Botões de ação](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#bot%C3%B5es-de-a%C3%A7%C3%A3o)
   1. [Regras para implementações](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#regras-para-implementa%C3%A7%C3%B5es)
      1. [Botões voltar](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#bot%C3%B5es-voltar)
      1. [Casos de múltiplos botões de submissão](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#casos-de-m%C3%BAltiplos-bot%C3%B5es-de-submiss%C3%A3o)
      1. [Casos de apresentação de botões de reset e submissão](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#casos-de-apresenta%C3%A7%C3%A3o-de-bot%C3%B5es-de-reset-e-submiss%C3%A3o)
   1. [Elementos de apresentação de lista de conteúdos](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#elementos-de-apresenta%C3%A7%C3%A3o-de-lista-de-conte%C3%BAdos)
      1. [Cards de conteúdo](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#cards-de-conte%C3%BAdo)
         1. [Regras de conteúdo](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#regras-de-conte%C3%BAdo)
         1. [Corpo de um card deve sempre possuir elementos mínimos](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#corpo-de-um-card-deve-sempre-possuir-elementos-m%C3%ADnimos)
         1. [Controles devem sempre estar presentes próximos em único local dentro do corpo de cada card](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#controles-devem-sempre-estar-presentes-pr%C3%B3ximos-em-%C3%BAnico-local-dentro-do-corpo-de-cada-card)
         1. [Animação de carregamento do card](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#anima%C3%A7%C3%A3o-de-carregamento-do-card)
         1. [Controle de reload de card](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#controle-de-reload-de-card)
   1. [Elementos de navegação](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#elementos-de-navega%C3%A7%C3%A3o)
      1. [Breadcrumb](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#breadcrumb)



# Definições e Especificações de aplicação

## Conteúdos complementares

### Definições de localização

Existem 4 áreas de apresentação definidas no projeto. Sendo elas, top, bottom, left, right. Abaixo as definições de cada uma:

| Posição | Título | Descritivo | Exemplo |
| -------- | ---------- | -------- | -------- |
| top | Conteúdos servidos com animação de cima para baixo | É utilizado para apresentar mensagens de informações de sucesso. | Ao salvar um formulário com sucesso. Ao requisitar informações complementares explicativas, como bloco de ajuda. Itens como estes devem ser usados para a apresentação do conteúdo top->down |
| bottom | Conteúdos servidos com animação de baixo para cima | É utilizado para apresentar informações de erros ou alertas significativos que em sua maioria informam ou impedem o prosseguimento de uma determinada funcionalidade ou ação | Ao submeter um formulário com erro, a mensagem de resposta de erro deve ser apresentada desta maneira, com conteúdo sendo exibido de baixo para cima |
| left | Menu de navegação lateral | Especificamente para uso do menu. É o conteúdo animado servidor da esquerda para direita. | |
| right | Conteúdos complementares do módulo | Em caso de necessidades de apresentações de elementos que sirvam conteúdos complementares ao módulo sendo visualizado, ele deve ser apresentado com animação da direita para esquerda, sem realizar atualização da tela. | Como exemplo, formulário de cadastro de conteúdos adicionais que serão utilizados para preencher campos do formulário que está sendo utilizado. Outro exemplo é o componente de upload de arquivos que é possível de ser utilizado sem sair do módulo que está carregado na tela |


### Mensagens em modal de erro

A apresentação de mensagens em modal de erro devem ser exibidas utilizando componente de apresentação down-to-top. Como descrito acima, ele utiliza a posição bottom.
Por padrão a mensagem de erro vem escrida dentro da tag `pre`.

![mensagem de erro aprensetada no modal](/uploads/601c78b541b501ffa5414cc57cdaf15d/Edit___Padrao_de_elementos___Wiki___infrashop___especificacao-funcional___GitLab_-_Google_Chrome_2017-09-29_16.21.13.png)

### Mensagens em modal de sucesso ou aviso complementares

A apresentação de mensagens desta maneira devem ser apresentadas utilizando conteúdo top-to-down.  Um exemplo de uso é a apresentação de conteúdos grandes de informações sobre determinada área do sistema.

### Menus de navegação lateral

O menu lateral de navegação deve estar sempre presente durante a utilização dos módulos, facilitando a navegação em ambiente mobile com todos os itens acessíveis pela apresentação padrão do tema utilizado na construção da interface.

### Conteúdo complementar do módulo

Conteúdos complementares devem ser sempre apresentados da direita para esquerda, utilizando bloco `aside` de conteúdo. A sua apresentação deve utilizar a animação padrão do tema utilizando na construção da interface.

Ele pode sofrer alterações de acordo com o tipo de conteúdo apresentado. Como por exemplo, apresentar ou não o `overlay` escuro com opacidade sobre o restante da página que estava sendo editado anteriormente, de acordo com a necessidade de utilização. Como exemplo, um upload de arquivos, salvo em necessidade de bloqueio da tela anterior ser explicito, deve sempre ocultar este `overlay` de forma que o usuário possa interagir com os dois blocos de interface do usuário.

A largura do conteúdo também pode variar. Em casos de conteúdo de pequenos campos necessários, pode ter uma largura menor que para um conteúdo de upload de arquivos. Orienta-se sempre utilizar não mais do que 50% da tela para essa apresentação.

Caso seja necessário um conteúdo complementar exibir um segundo conteúdo complementar, acima do já existente, ele deve estar sobreposto mas não ocupar a mesma largura. Orienta-se sempre que ele tenha ao menos 50px menos espaço em eixo "x" do que o conteúdo que já estava visível.


# Recursos de formulário

## Controle de texto com auto-complete de conteúdo (`input-search`)

Utilizado em necessidades de apresentação de um campo de texto aberto, para ao que o usuário informe algumas letras do texto que deseja informar, uma lista de opções é apresentado, dando a possibilidade do usuário selecionar um valor que auto-complete o restante da informação no campo de controle.

É usado especificamente em situações onde o usuário pode informar qualquer valor no campo, não se limitando apenas ao valor informado pelo auto complete.

Este campo se utiliza de requisições assíncronas externas a página para buscar os valores que devem ser apresentados.

## Lista de seleção única com busca auto-complete (`select-search`)

Utilizado em necessidades de apresentação de um campo de seleção onde os valores de possíveis seleção são entregues junto ao carregamento do conteúdo. Ou seja, não depende de requisições assíncronas para apresentação dos valores enquanto o usuário digita no campo de busca.

Quando usuário inicia a digitação, o próprio componente controle, no front-end, faz a separação dos valores que fazem semelhança ao conteúdo informado, ocultando os demais itens.

## Lista de seleção única (`select`)

Utilizando quando deseja-se apresentar opções para usuário selecionar de forma única. De maneira que possa selecionar apenas uma opção de uma lista, pequena ou grande, de opções.

## Lista de seleção múltipla (`tags`)

Utilizado para apresentação de seleção de múltiplas opções, com ou sem previa lista de opções.

### Com lista prévia de opções (`tags-search`)

Ao que é realizada a digitação no campo de entrada de dados, as opções correlatas ao assunto são filtradas e apresentadas no campo para o usuário selecionar.

Após selecionado é apresentado em formato de tag cada opção seleciona. Adicionalmente pode ser apresentado quando `mouse-hover` informações adicionais sobre a tag.

### Sem lista prévia de opções (`tags-live`)

Não é apresentado opções quando usuário digita informações no campo de entrada de dados. E ao que ele executa (pressiona) teclas de finalização (vírgula, tag ou enter) a inserção da tag é finalizada, possibilitando a inserção de novas tags.

Não se faz necessário para este caso o uso de conteúdo informativo com `mouse-hover` nas tags inseridas neste controle.

**Nota 1**: Pode ser ser configurado para que o usuário possa selecionar apenas uma tag em situações de dependência de outra informação. Mas orienta-se utilizar este conteúdo apenas para seleção múltipla de itens.

## Lista de seleção múltipla em árvore (`tree-view`)

A lista de seleção múltipla em árvore é utilizada para apresentar informações que possuem referência de estrutura de diretórios. Como por exemplo é a apresentação de lista de categorias que apresenta um ou mais sub-níveis.

## Seleção de valores boleano (`input-checkbox`)

É utilizado quando há necessidade de apresentação de 1 ou mais controles de seleção VERDADEIRO ou FALSO, expressando a possibilidade que o valor foi incluído/selecionado (VERDADEIRO) ou não incluído/não selecionado (FALSO).

Ele pode ser apresentado com uma ou mais opções num mesmo bloco de apresentação. Porém trabalhando separadamente sem afetar os demais itens.

É orientado a sua aplicação em campo que expressem conteúdo: Incluir/Não incluir, Selecionar/Não selecionar, Concordo/Discordo, Aceito/Não aceito, e similares.

![input-checkbox](/uploads/375dacf610f3ae0cf82ce9c5fa5a4e9e/Pages_-_Admin_Dashboard_UI_Kit_-_Form_Elements_-_Google_Chrome_2017-09-29_16.31.51.png)

## Seleção de valores boleano de status (`switch`)

Este controle de formulário é facilmente reconhecido pelo seu aspecto parecido ao layout apresentando em dispositivo com sistema operacional iOS. Abaixo dois exemplo de aplicação:

![image](/uploads/d41ede899a7a3dfe50c1178e7c1451b2/image.png)

Ele é utilizado exclusivamente em situações onde o controle possui apenas uma opção com valores VERDADEIRO ou FALSO. Distingui-se de campos de `input-checkbox` quando um determinado controle pode exibir mais de um checkbox para o mesmo campo de informações.

![image](/uploads/350322fa0e7b324d04178bd567c949d0/image.png)

É orientado a sua aplicação em campos que expressem o conteúdo: ativo/inativo, visível/invisível, ligado/desligado e similares.

### Cores 

Como padrão para cor complementar de formulário, deve seguir as cores indicadas na tabela do tópico [Botões de ação](https://gitlab.infracommerce.com.br/infrashop/especificacao-funcional/wikis/easyadmin/padrao-de-elementos#bot%C3%B5es-de-a%C3%A7%C3%A3o) para o item `complement`


## Seletores múltiplos de única opção (`input-radio`) 

Controle para apresentar lista de opções visíveis e únicas. O usuário é capaz de visualizar todos os itens apresentados, e notoriamente saber que somente uma das opções pode ser selecionada.

Recomenda-se a utilização deste item para casos em que poucas opções podem ser selecionadas (não mais do que 5 opções). Para casos de muitas opções, recomenda a utilização de `select`

![input-radio](/uploads/f7a4f24f678e977c48fc215346e79f5a/Pages_-_Admin_Dashboard_UI_Kit_-_Form_Elements_-_Google_Chrome_2017-09-29_16.33.02.png)

## Ícones em controles de formulário

Podem ser utilizados ícones em controles de formulário de acordo com a necessidade de expressar detalhes para o usuário entender o tipo de preenchimento que deve realizar.

Regras para ícones de ação:

* Como padrão para cor complementar de formulário, deve seguir as cores indicadas na tabela do tópico `Botões de ação` para o item `complement`
* Devem ser posicionados na direita

![image](/uploads/1010f88c007cd5758dee0721265dac00/image.png)

Regras para ícones de informação complementar para cliente preencher o campo

* Como padrão para cor complementar de formulário, deve seguir as cores indicadas na tabela do tópico `Botões de ação` para o item `reset`
* Devem ser posicionados na esquerda

![image](/uploads/685b93caa36c0f004333afe071048d74/image.png)

## Links em controles de formulário

Em casos onde é necessário apresentar um botão complementar no campo de entrada (definido em `Ícones em controles de formulário`) porém com menos destaque, é utilizado então um link junto a `label` do controle. Desta forma mantendo a funcionalidade mas removendo o destaque desnecessário para o controle.

A cor a ser utilizada nele deve ser a cor `insert` definida na planilha de `Botões de ação`

Exemplo:

![image](/uploads/10acd967bed6f7d60817d2b3c236ef39/image.png)

## Textos de ajuda para preenchimento de campos (`control-help`)

Pode ser apresentado textos de ajuda em cada campo de um formulário. Como padrão deve ser utilizado sempre o modelo de apresentação abaixo do campo de controle de entrada. Como exemplo abaixo:

![image](/uploads/07f25bf7638dc10360217c138df0eec9/image.png)

## Textos de informações complementares para preenchimento de campos (`control-tooltip`)

Para textos que levem informação complementar de um determinado controle para o usuário, e que este texto tenha não mais que 100 caracteres, ele pode ser apresentado em forma de `tooltip` para que o usuário possa ao `mouse-hover` ou efetuar um `tap` o tootlip seja exibido com a informação.

Deve existir ao lado da label do campo de entrada um ícone com uma exclamação. Este ícone é responsável pela ativação do tooltip.

Exemplo:

![image](/uploads/a43a85e3b2cdeeabd391ad22b10a78b0/image.png)

## Apresentação de controle com erro de preenchimento (`has-error`)

Para apresentação de erros em campos únicos de formulário deve ser apresentado uma borda ao redor do campo, utilizando o padrão do theme que é de coloração avermelhada. E também uma mensagem informativa abaixo do campo.

![image](/uploads/a3a27480cf78b634a7fcb5a9a3b7ec84/image.png)

## Apresentação de controle com warning de preenchimento (`has-warning`)

Para apresentação de warnings em campos únicos de formulário deve ser apresentado uma borda ao redor do campo, assim como no item acima, utilizando o padrão do theme que é de coloração alaranjada. E também uma mensagem informativa abaixo do campo.

![Novo_-_Banners_-_Infracommerce_-_Google_Chrome_2017-09-29_16.45.40](/uploads/71ef731c503ca024bb2ba10054c0ab7a/Novo_-_Banners_-_Infracommerce_-_Google_Chrome_2017-09-29_16.45.40.png)

# Ações de formulário

## Apresentações de mensagens de validação de campos de formulário

Ver item `has-error`

## Botões de ação

`📌  TODO: Complementar as cores na tabela`

| Nome | detalhes | Ação esperada | Cor | Label | class do theme | class complementar do theme |
| ------ | --- | --------------- | --- | ------ | -------| ------ | -------|
| submit | botão principal do formulário principal | | | .btn-primary | não deve ter complementar |  |
| reset | |  | | .btn-default |  |  |
| save | | | | .btn-primary |  | .btn-complete |
| insert | | | | .btn-primary |  |  |
| update | | | | .btn-primary |  |  |
| back | | | | .btn-primary | complementar, deve ser um link |  |
| delete | | | | .btn-danger |  | .btn-info |
| complement | Utilizado no meio dos formulário para ações específicas, como por exemplo abrir um conteúdo complementar, ou elementos como `switch` ou ícones em input-controls  | | | .btn-success | não deve ter complementar | |


## Regras para implementações

### Botões voltar

Existem dois casos que podem ser usados de botões voltar. Em ambos, ele deve ser posicionado na esquerda.

Primeiro caso é o botão voltar ser realmente um botão. Regras neste caso:

* Estar na esquerda
* Utilizar o modelo de cores padrões definidos na tabela acima

Segundo caso, é botão voltar estar ao lado dos botões de submissão. Regras para este caso:

* Não deve ser usado botão, e sim deve transformar o botão em um `link`com a class visual `.text-complete`

Preferência é utilizar o primeiro caso.

### Casos de múltiplos botões de submissão

Exemplo: `submit` e salvar como rascunho

Ambas as ações destes botões servem para submeter a informação. Neste caso onde é necessário a utilização de dois botões na mesma área visual, o botão salvar como rascunho deve utilizar a sua cor complementar conforme a tabela acima.

`📌  TODO: adicionar imagem exemplo`


### Casos de apresentação de botões de reset e submissão

Deve seguir o mesmo descrito para os múltiplos botões de submissão, exceto que o botão de reset deve utilizar sua class visual de acordo com a tabela acima indicada.


# Elementos de apresentação de lista de conteúdos

## Cards de conteúdo

Os cards de conteúdo são os principais modelos de apresentações de lista de itens dentro do sistema. Sua apresentação define o modelo de informações que o usuário pode rapidamente ver seu conteúdo, entender o que é apresentado e interagir por meio de principais controles disponíveis para cada tipo de dado apresentado.

Cards são utilizando normalmente em telas de listagem de itens de um módulo, apresentando seus elementos principais, filhos do módulo em questão. Como por exemplo, módulo de banners, cada banner é apresentado como um card de conteúdo. O mesmo se repete em, por exemplo, promoções, templates de banner, entre outros.

### Regras de conteúdo

Para que seja possível seguir um padrão entre telas de conteúdo, é definido abaixo regras para que seja utilizada a apresentação dos dados de cards em cada página.

#### Corpo de um card deve sempre possuir elementos mínimos

Os elementos mínimos são definidos por:

* Cabeçalho: Onde é apresentado o título principal do conteúdo e um botão de ação ou texto indicando o status;
* Corpo: Onde é apresentado conteúdos específicos para cada tipo de card de acordo com seu módulo;
* Rodapé: Onde é apresentado controles complementares, como clone, edição, visualização rápida e similares;

![Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_11.06.38](/uploads/96c0ea94f06417b3fdf36118b2fd46bd/Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_11.06.38.png)

#### Controles devem sempre estar presentes próximos em único local dentro do corpo de cada card.

Como indicado acima, controles de card devem sempre ficar no espaço de rodapé do card. Desta maneira podemos associar ao usuário que controles sempre ficarão neste local, de fácil acesso igual em todas as telas.

Devem ser utilizados ícones de acordo com a necessidade de cada ação. As ações devem ser ações rápidas que não necessitam de detalhamento técnico para entender o que ela faz. Por exemplo, ativar/desativar pode estar presente neste bloco. Caso seja uma ação que envolva outros conteúdos complementares ou explicações que não caibam em um tooltip, essa ação não pode estar neste bloco, e sim dentro da tela de alterações do item principal deste card.

Exemplo de controles:

| Nome | Ação | Detalhes | Imagem exemplo |
| ---- | ---- | -------- | -------------- |
| `switch` | Ativar/Desativar | Deve ser utilizado para ações de liga/desliga. Pelo espaço empregado para essa parte, deve ser usado o `switch` de tamanho menor, como na imagem ao lado | ![image](/uploads/0cca997cd432bc4ad92c168fb16132b6/image.png) |
| `fa-pencil` | abrir edição | Abre a tela de edição | ![fa-pencil](/uploads/71ab1a013bbab429e41be23976e0a221/Banners_-_Infracommerce_-_Google_Chrome_2017-09-29_16.57.49.png)|
| `fa-clone` | clonar dados do card | Abre uma tela de adição preenchida com os dados do card selecionado | ![fa-clone](/uploads/b236e6cde301169f5e5eb2927f9190fc/Banners_-_Infracommerce_-_Google_Chrome_2017-09-29_16.58.01.png)|
| `fa-expand` | Exibir dados do card | Abre um modal que ocupada a tela toda com os dados do card selecionado | ![fa-expand](/uploads/50dc7df385ab651cc1cbd41aec8019d2/Banners_-_Infracommerce_-_Google_Chrome_2017-09-29_16.57.39.png)|
| `fa-warning` | Abre conteúdo complementar | Abre um conteudo complementar | ![fa-warning](/uploads/c7e8f2ac8a8e140b4920f92c71071323/Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_10.57.20.png)|
| `fa-stop` | Cancela um processo | Relacionado a um processo em execução, tem função de cancelar o mesmo | ![fa-stop](/uploads/0201d7c507eddfcde19d9d841621b882/Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_10.57.47.png)|
| `progress-bar` | Status de carregamento de um processo | Apresenta o status de carregamento de um processo | ![progress-bar](/uploads/cc2c0e4a59456c94ce5d0d3b1aacb036/Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_10.59.57.png)|

Ordem de exibição dos controles no footer do card deve seguir a imagem abaixo:

![Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_11.06.13](/uploads/9e5359189d4a9770e5b1cc4c750a7647/Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_11.06.13.png)

##### Animação de carregamento do card

Existem casos onde os dados do corpo do card podem demorar para serem  obtidos. Para estes casos é utilizado uma animação de carregamento para indicar que o card ainda está sendo renderizado. O padrão aplicado é o mesmo de reload do `theme pages`, no entanto não conta com o icone para forçar o reload do card.

![Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_11.29.00](/uploads/b3309572a79d634ae8ab743ba08ec145/Gestão_de_Tabelas_de_Frete_-_Infracommerce_-_Google_Chrome_2017-10-02_11.29.00.png)

##### Controle de reload de card

O único controle que indicamos estar presente no cabeçalho de um card é o ícone de `reload`. Ele é padrão do `theme Pages` e é indicado para blocos que podem ter seu conteúdo atualizado para apresentar informações ao usuário. Exemplo de aplicação:

![screencast_2017-08-14_17-00-28](/uploads/057f0b151a97366bc534ad049c773cd3/screencast_2017-08-14_17-00-28.gif)


## Elementos de navegação

### Breadcrumb

O modelo de `breadcrumb` que deve ser utilizado será o mesmo modelo apresentado na imagem abaixo:

![image](/uploads/ff213dc523d7615095b5af7558d6f023/image.png)

* Não será utilizando ícones nos itens do breadcrumb.
* Sempre o último ítem do breadcrumb terá sua cor destacada indicando qual é a tela que está sendo visível

Exemplos para tela de adição de um item de um determinado módulo

>  Home > Banners > `Adicionar`

>  Home > Banners > `Editar (#XXXX)`

Obs: o `(#XXXX)` acima, identifica o ID que está sendo alterado.


