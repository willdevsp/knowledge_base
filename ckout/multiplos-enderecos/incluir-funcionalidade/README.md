# Múltiplos Endereços - Inclusão de funcionalidade em outras lojas

# Definição
Este documento tem como objetivo auxiliar na inclusão da funcionalidade de multiplos endereços em outras lojas.

As telas geradas para manutenção de multiplos endereços foge da construção padrão utilizando JSF os MB. 
Na implementação atual, é utilizado HTML para construção do "corpo" da página, que será populado via java script.
Toda a comunicações entre Front e Backend (ckout) é realizado via Api REST.  

# Requisitos 

* ifc-rest-service-1.11.0 ou versão superior.

# Início

Utilizaremos como base a versão que foi implementada na Unielever-CO que pode ser encontrada através do repositório 
```
https://gitlab.infracommerce.com.br/store-unileverco/unileverco-front
```
# Configuração do General Parameter (GP)

Para o uso da funcionalidade de multiplos endereços é necessário fazer uma configuração no GP CLIENT_ADDRESS_CONFIG da loja em questão.
Os parametros **"checkWarehose"** e **"setAsMainAddressOnlyOnSelect"**  dentro de **"COMPANY"** deve(m) ser alterado(s) para **true** (ou incluidos caso não existam). 

```js
{
   "edit": true,
   "create": true,
   "select": true,
   "autoSelect": true,
   "deselectOnSimulate": true,
   "clearCartOnAddressChange": "true",
   "configByCustomerType": {
       "PERSON": [{
           "edit": true,
           "editMainAddress": true,
           "create": true,
           "select": true,
           "autoSelect": false,
           "deselectOnSimulate": false
       }],
       "COMPANY": [{
           "edit": true,
           "editMainAddress": true,
           "setAsMainAddress": true,
           "setAsMainAddressOnlyOnSelect": true,
           "validatePostalCode": false,
           "create": true,
           "select": true,
           "autoSelect": true,
           "deselectOnSimulate": true,
           "allAddressInSameState": false,
           "allAddressInSameCountry": true,
           "checkWarehouse": true
       }]
	} 
}
```


# Replicação tela "Meus Endereços" 
1) Replicar o arquivo **/sserv/xhtml/address.xhtml**

Como não utilizaremos JSF, precisamos manter apenas a estrutura básica da página de endereço. Os componentes como listas, botões, formulários serão renderizados em tempo de execução via javascript.

2) Replicar o arquivo **/htdocs_src/desktop/js/sserverAddress.js**.

Esse arquivo é responsável por renderizar os componentes da página de endereço, bem como realizar as chamadas as API Rest que retornarão os endereços e realizarão as funcionaliades de CRUD de novos endereços. 

3) Garantir que o arquivo **sserverAddress.js** seja acessivel no contexto do frontend. 

Caso esse arquivo não esteja acessivel no front, a chamada para inicialização do **sservAddress** não será realizada e consequentemente os componentes da tela não serão carregados.

4) Para inicialização do compontente sserv é necessário realizar a seguinte chamada:
```js
window.sservAddress.init();
```

Na loja UnieleverCO realizamos a chamada dessa função através dos arquivos **/htdocs_src/desktop/js/unieleverco-common.js** e **/htdocs_src/mobile/js/store-common.js**.

# Replicação modal "Tienda Activa"
Editar o arquivo **htdocs_src/desktop/js/custom-customer-register.js**

Na função **submitLogin** deve ser substituido o seguinte trecho de código

```js
if (!!window.afterAuth) {
    window.afterAuth(response);
    return true;
} else {
    window.location.href = acecIndexInformation.catalogDomain + (!!$.cookie('urllastcategoryvisited') ? $.cookie('urllastcategoryvisited') : '');
    return true;
}
```

Por 

```js
if (!!window.afterAuth) {
    window.afterAuth(response);
    return true;
} else {
    window.sservAddress.tiendaActiva(response.data.customer);
    return true;
}
```

# Articles

## Incluir combo box no Header da Aplicação

É necessário acessar o Admin da Loja em questão e adicionar o seguinte trecho de código no Article **header-page-catalog**

```html
<div id="addressContentSelect">
    <button class="mainAddressSelect">Cargando direcciones ...</button>
    <ul class="delivery-list">
</div>
```

## Adicionar novo article combobox para mobile

É necessário acessar o Admin da Loja em questão e adicionar um novo Article **mobile-combobox-multi-address**

```html
<div id="addressContentSelect">
    <button class="mainAddressSelect">Cargando direcciones ...</button>
  <ul class="delivery-list"></ul>
</div>
<script>
	window.loginModalEnabled = true;
</script>
```

# Observações

* Para a implementação utilizada como excemplo o CSS está disponivel no projeto 
```
https://gitlab.infracommerce.com.br/store-unilever/unilever-front.git
```
* Para implementação da versão Mobile, deve ser seguida a mesma logica acima, apenas atentando-seque deve ser utilizado o arquivo *address**m**.xhtml*

* Validações de Postal Code devem ser feita conforme demandado por cada loja. No exemplo em questão UnileverCO, ao invés de passarmos o Postal Code (CEP) para recebermos o endereço, passamos o endereço e recebemos o Postal Code da Colombia. 