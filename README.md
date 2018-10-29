# Infrashop Knowledge Base (Infrashop KB)

Para ir direto para a lista de tópicos: [⬇ Tópicos](#tópicos)

## Definição
O Infrashop KB é o repositório que contém toda a base de conhecimento da Infrashop.

Dentra a base de conhecimento existem artigos, tutoriais, referências para outras documentações e toda a documentação disponível sobre a Infrashop.

A linguagem utilizada para escrever a documentação é o Markdown. Caso tenha dúvidas sobre como fazer a documentação utilizando Markdown existem diversos links de apoio na internet, seguem exemplos:
*  [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
*  [Markdown Quick Reference](https://en.support.wordpress.com/markdown-quick-reference/)
*  [Editor online, com grande variedade de exemplos](https://stackedit.io/app)

## Direcionamento

Caso a documentação não exista nesse projeto ela deve ser criada, mesmo que seja apenas para referenciar o TWiki ou Infrapedia ou SVN ou qualquer outro lugar.

Caso a documentação já exista e a sua atividade gerou a necessidade de atualizá-la, por favor mantenha esse repositório atualizado para que as outras pessoas possam chegar na informação sem a necessidade de parar você. =]

## Como posso colaborar?

O *git flow* adotado para esse projeto é muito simples:

![git-flow](./git-flow.png)

1.  Crie uma branch a partir da `master`.
    *  Utilize o mesmo nome da branch de desenvolvimento para facilitar o rastreio
2. Crie / atualize a documentação
3. Faça um *Merge Request* de volta para a `master` e delegue-o para o *scrum master* da sua equipe

Após o *scrum master* aprovar o MR sua documentação estará disponível para todos. =]

Também é possível utilizar as **Issues** para documentar FAQs para serem facilmente compartilhados com a equipe.

Para ler mais sobre as issues [clique aqui](issues/README.md).

# Tópicos

## Geral
### [Envio de Emails](emails/README.md)
### [Parâmetros (general parameters)](general-parameter/README.md)


## Catálogo
### [Agrupamentos de Produtos](catalog/agrupamento_produtos/README.md)

## Integrações
### [Mercury](mercury/README.md)
### [Middleware B2B](b2b/README.md)
### [Microservices](microservices/README.md)

## Camada de Vendas
### [Cliente](customer/README.md)
### [Meios de Pagamento](ckout/payments/README.md)
### [Motor de Regras Dinâmicas (drools)](drools/README.md)
### [Múltiplos Endereços](ckout/multiplos-enderecos/README.md)
### [Store Front](storefront/README.md)

## Camada Administrativa
### [EasyAdmin](easyadmin/README.md)
