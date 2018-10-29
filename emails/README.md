# Emails

## Sumário
- [Fluxo](#Fluxo)
- [Templates](#Templates)
- [Variáveis](#variaveis)

## Fluxo
O fluxo de envio de email inclui fases como a criação da mensagem para envio de email, envio da mensagem para o BUS do sistema, envio para o JMS, renderização do email a partir do template e atributos enviados e o envio do email ao cliente. Mais detalhes do fluxo podem ser achados no link abaixo:

[Fluxo de envio de emails](./email-flow.md)

## Templates

O Velocity está configurado para recuperar os templates da tabela ECAD_EMAIL_TEMPLATE, onde o ID do template está no campo SOURCE_NAME.

| Identificalção do template | Descrição  | 
|---|---|
|ORDER_INCLUDED |	Pedido incluido|
|ORDER_CANCELED |	Pedido cancelado|
|ORDER_APPROVED |	Pedido aprovado|
|ORDER_DELIVERED |	Pedido entregue|
|ORDER_DISPATCHED |	Pedido despachado|
|ORDER_NOT_APPROVED |	Pedido não aprovado|
|ORDER_UNSUCCESSFUL_DELIVERY |	Problema na entrega de pedido|
|ABANDONED_CART |	Carrinho abandonado|
|ADMIN_SEND_PASSWORD_BY_MAIL |	Envio de senha por e-mail|
|SEND_RECOMMENDED |	Produto recomendado|
|RETURN_ITEM |	Trocas e devoluções|
|RETURN_ITEM_SAC |	Trocas e devoluções - SAC|
|SEND_CONTACT_US |	Contate-nos|
|SEND_CREATE_USER_BY_MAIL |	Criação de um novo usuário|
|SEND_CONFIRMATION_MAIL_BY_MAIL |	Confirmação de e-mail|
|SEND_PASSWORD_BY_MAIL |	Envio de senha|
|SEND_LOGIN_BY_MAIL |	Envio de login por e-mail|
|SEND_NUMBER_VOUCHER_BY_MAIL |	E-mail enviado para o cliente quando um vale troca é criado aprovado|
|NOTIFY_BILL_PEND_PAY |	Envio e-mail para relembrar cliente com boleto pendente pagamento|
|ORDER_NEAR_SHOP |	E-mail enviado para lojistas que estão perto de pedidos aprovados em lojas que possuem o Omni Channel|
|ORDER_CAPTURED_SHOP |	E-mail enviado para o cliente quando um lojista captura o seu pedido no fluxo do Omni Channel|
|B2B |	Envio de e-mail para pareria B2B|
|SEND_NUMBER_VOUCHER_WEDDING_LIST_BY_MAIL |	Envio com as informações do voucher gerado para os noivos após a compra de um produto da lista de casamento|
|SEND_INVITE_GUEST_WEDDING_LIST |	Envio de e-mail para os convidados da lista de casamento|
[[⬆︎ Topo]](#Sumário)

## Variaveis

### Para utilizar qualquer atributo nos emails, basta utilizar $attributes.get("NOME\_DA\_VARIAVEL").get("value").

### ABANDONED\_CART

*   GUEST\_NAME - Nome do usuário
*   PRODUCT\_IMAGE - Imagem de Produto Tamanho GM
    
    * * *
    

### ADMIN\_SEND\_PASSWORD\_BY\_MAIL

*   CUSTOMER\_NAME - Nome do Cliente
*   CUSTOMER\_LOGIN - Login de Acesso do Cliente
*   CUSTOMER\_PASSWORD - Senha de Acesso do Cliente
    
    * * *
    

### NOTIFY\_BILL\_PEND\_PAY

*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id de Pedido
*   ORDER\_DAY - Dia de Vencimento do Pedido
    
    * * *
    

### NOTIFY\_PRODUCT\_AVAILABLE

*   CUSTOMER\_NAME - Nome do Cliente
*   SKU\_IMAGE\_MGG - Imagem de produto Tamanho MGG
*   PRODUCT\_SELLING\_TITLE - Título de Venda do Produto
*   PRODUCT\_URL - URL do Produto
    
    * * *
    

### ORDER\_APPROVED

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
    
    * * *
    

### ORDER\_CANCELED

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
    
    * * *
    

### ORDER\_DELIVERED

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
    
    * * *
    

### ORDER\_DISPATCHED

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
*   TRACKING\_CODE - Código de Rastreio
    
    * * *
    

### ORDER\_INCLUDED

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido

### ORDER\_NOT\_APPROVED

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
    
    * * *
    

### RETURN\_ITEM

*   ORDER\_XML - XML do Pedido
*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
*   MOTIVE - Motivo da Desistência de Compra
*   MOTIVE\_DESCRIPTION - Descrição do Motivo da Desistência de Compra
    
    * * *
    

### RETURN\_ITEM\_SAC

*   CUSTOMER\_NAME - Nome do Cliente
*   ORDER\_ID - Id do Pedido
*   MOTIVE - Motivo da Desistência de Compra
*   MOTIVE\_DESCRIPTION - Descrição do Motivo da Desistência de Compra
*   CUSTOMER\_EMAIL - Email do Cliente

### SEND\_CONFIRMATION\_MAIL\_BY\_MAIL

*   CUSTOMER\_NAME - Nome do Cliente
    
    * * *
    

### SEND\_CREATE\_USER\_BY\_MAIL

*   CUSTOMER\_NAME - Nome do Cliente
    
    * * *
    

### SEND\_NUMBER\_VOUCHER\_BY\_MAIL

*   NICKNAME - Nome utilizado no login do cliente
*   VOUCHER\_ID - Número do vale troca
*   VOUCHER\_VALUE - Valor total do vale troca
*   EXPIRATION\_DATE - Data de expiração do vale troca

### SEND\_PASSWORD\_BY\_MAIL

*   CUSTOMER\_NAME - Nome do Cliente
*   CUSTOMER\_LOGIN - Login de Acesso do Cliente
*   CUSTOMER\_PASSWORD - Senha de Acesso do Cliente
    
    * * *
    

### SEND\_RECOMMEND

*   NAME\_TO - Nome DE:
*   NAME\_FROM - Nome PARA:
*   COMENT - Comentário
*   PRODUCT\_NAME - Nome do Produto
*   SKU\_IMAGE\_MGG - Imagem de produto Tamanho MGG
*   PRODUCT\_URL - URL de produto

### SEND\_NUMBER\_VOUCHER\_WEDDING\_LIST\_BY\_MAIL

*   FULLNAME - Nome completo do noivo
*   NICKNAME - Nome utilizado no login do noivo
*   VOUCHER\_ID - Número do voucher
*   VOUCHER\_VALUE - Valor total do voucher
*   EXPIRATION\_DATE - Data de expiração do voucher
*   CUSTOMER\_ID - Número de identificação do noivo
*   VOUCHER\_SUBTYPE - Tipo do voucher
*   CREATION\_DATE - Data da criação do voucher
*   ORDER\_ID - Número de identificação do pedido
*   ORDER\_XML - XML do pedido

### SEND\_INVITE\_GUEST\_WEDDING\_LIST

*   FULLNAME - Nome completo do convidado da lista de casamento
*   URL\_WEDDING\_LIST - URL para acesso a lista de casamento
*   GROOM\_NAME - Nome do noivo
*   BRIDE\_NAME - Nome da noiva
