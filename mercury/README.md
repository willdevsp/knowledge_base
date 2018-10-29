# Mercury

## Sumário
- [Arquitetura Mercury](#arquitetura-mercury)
  - [Autenticação Oauth](#autenticação-oauth)

## Arquitetura Mercury

Visão geral da arquitetura Mercury no TWiki:

*  https://lab.accurate.com.br/twiki/bin/view/Main/AcecArchitectureMercury

### Autenticação Oauth

Todas as APIs que tiverem como dependência o `ifc-security-auth` irão expor automaticamente a API `/oauth/token`.

Ex:

```shell
curl -k "http://adserv-unilever-dev.infracommerce.com.br/ifc-integration-b2b-api/oauth/token?client_id=clientapp&client_secret=123456&grant_type=password&scope=read%20write&username=UNILEVER%5Cunilever&password=infrashop14"
```

Essa API recebe os seguintes parâmetros:

| Parâmetro | Descrição  | 
|---|---|
|client_id |	Valor padrão: clientapp|
|client_secret |	Valor padrão: 123456|
|grant_type |	Valor padrão: password|
|scope |	Valor padrão: read write|
|username |	Nome do usuário|
|password |	Senha do usuário|

A API `ifc-security-auth` roda tanto em APIs da camada SL quanto AD, portanto é possível realizar a autenticação em ambas camadas.

#### Autenticação na camada AD
Na camada AD a autenticação é realizada na `ECAD_USER`, ou seja, o `username` e o `password` correspondem aos campos `ECAD_USER.NAME` e `ECAD_USER.PASSWORD`.

As credenciais (_roles_) do usuário são recuperadas a partir do perfil do usuário: `ECAD_USER > ECAD_PROFILE_FUNCTIONALITY > ECAD_FUNCTIONALITY`.

#### Autenticação na camada SL
Na camada SL a autenticação é realizada nas tabelas `ECSL_CUSTOMER_LOGIN` e `ECSL_SALES_ASSISTANT_USER`.

Na camada SL o usuário pode ser de três tipos diferentes:
*  Cliente comum
*  Cliente guest
*  Usuário de venda assistida

Quando a aplicação realiza a autenticação na camada SL ela tenta realizar a autenticação de acordo com a ordem acima, ou seja:
*  Primeiro testa se o usuário e senha é de um cliente comum (`ECSL_CUSTOMER_LOGIN / ECSL_CUSTOMER.guest='N'`)
*  Depois testa se o usuário e senha é de um cliente guest (`ECSL_CUSTOMER_LOGIN / ECSL_CUSTOMER.guest='Y'`)
*  Por fim testa se o usuário e senha é de um usuário de venda assistida (`ECSL_SALES_ASSISTANT_USER`).

As credenciais (_roles_) do usuário na camada SL podem ser as seguintes:
*  Cliente comum: _ROLE_Customer_
*  Cliente guest: _ROLE_Guest_
*  Usuário de venda assistida: _ROLE_SalesAssistant_

**OBS:** A autenticação na camada SL está disponível a partir da versão `1.13.0` do `ifc-security-auth`.

[[⬆︎ Topo]](#sumário)