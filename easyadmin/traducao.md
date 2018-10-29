# Como realizar a tradução

Este documento contém informações de como realizar a tradução do arquivos de linguagem utilizados do Easy Admin.

## Fluxo da tradução

1. Os arquivos de tradução serão gerados pelo desenvolvedor, conforme explicado na [documentação de internacionalização](easyadmin/internacionalizacao), e disponibilizados no repositório [translate](https://gitlab.infracommerce.com.br/easy-management/translate).

2. O responsável pela tradução deve, clonar o repositório em sua máquina, e sempre atualiza-lo antes de iniciar o processo de tradução. Se preferir pode realizar a tradução pela interface do GitLab. O arquivo está em formato JSON, e pode ser editado em qualquer editor de texto.

3. Ao finalizar a tradução, fazer o commit dos arquivos alterado no repositório *translate*.

4. O desenvolvedor responsável, deve copiar os arquivos traduzidos para dentro do módulo do correspondente.

### Instruções

**1. Não alterar o texto que vem antes do : (dois pontos)**

O texto da tradução deve ser inserido dentro das aspas que estão do lado direto do : (dois pontos). O texto a esquerda é a chave de replace e não deve ser alterado.

**2. O !! indica que o texto ainda não foi traduzido**

Quando o texto do lado direto, inicia com !! (duas exclamações) indica que ele ainda não foi traduzido. Após realizada a tradução essas exclamações devem ser removidas.

**3. Variáveis**

Quando uma palavra está entre dois asteriscos significa que essa palavra é uma variável, e não deve ser alterada.

Exemplo:

```json
"A posição *POSITION* não existe.": "!!A posição *POSITION* não existe."
```

Nesse caso a palavra *POSITION* não deve ser traduzida, pois no momento da execução do script ela será substituída pelo nome da posição. Ela pode ter sua posição no texto alterada conforme caso seja necessário.

**4. Localização dos arquivos para tradução**

Os arquivos para tradução estão localizados no repositório [translate](https://gitlab.infracommerce.com.br/easy-management/translate), é possível fazer o download dos arquivos ou traduzir diretamente pela interface do gitlab.

É importante ter cuidado para não alterar a estrutura de pastas e a nomenclatura dos arquivos.

## Exemplo de arquivo de tradução

```json
{
  "404 - Banners": "!!404 - Banners",
  "A posição *POSITION* não existe.": "!!A posição *POSITION* não existe.",
  "Abrir árvore de categorias": "!!Abrir árvore de categorias",
  "Adicionando novo banner": "!!Adicionando novo banner",
  "Adicionando novo banner clone de": "!!Adicionando novo banner clone de",
  "Adicionar": "!!Adicionar",
  "Ativo": "!!Ativo",
  "Ativo?": "!!Ativo?",
  "Banner": "!!Banner",
  "Banner inserido com sucesso!": "!!Banner inserido com sucesso!",
  "Banner salvo com sucesso!": "!!Banner salvo com sucesso!",
  "Banners": "!!Banners",
  "Data de apresentação": "!!Data de apresentação",
  "Data de apresentação do banner": "!!Data de apresentação do banner",
  "Editando banner": "!!Editando banner",
  "Editar": "!!Editar",
  "Editar - Banners": "!!Editar - Banners",
  "Editar em modo avançado?": "!!Editar em modo avançado?",
  "Enviar/Exibir lista de Arquivos": "!!Enviar/Exibir lista de Arquivos",
  "Este template não permite edição em modo avançado": "!!Este template não permite edição em modo avançado",
  "Keywords": "!!Keywords",
  "Preview": "!!Preview",
  "Página": "!!Página",
  "Páginas": "!!Páginas",
  "Salvar": "!!Salvar",
  "Selecionar Categorias": "!!Selecionar Categorias",
  "Selecione": "!!Selecione",
  "Sim": "!!Sim",
  "Status do banner alterado com sucesso.": "!!Status do banner alterado com sucesso.",
  "Título do Banner": "!!Título do Banner",
  "Visualização não disponível.": "!!Visualização não disponível."
}
```