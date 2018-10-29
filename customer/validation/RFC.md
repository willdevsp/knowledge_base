# **Validação RFC (México)**

## O que é RFC(Registro Federal de Contribuintes)?

É uma chave única exigida para qualquer transação econômica no México, seja pessoa física ou jurídica. É um código tributário expedido pelo SAT - Serviço de Administração Tributária.

A estrutura do RFC varia de acordo com o tipo de pessoa.

**Pessoa física** - consiste de 13 caracteres (4 letras, 6 dígitos e 3 caracteres alfanuméricos).

**Pessoa jurídica** - consiste de 12 caracteres (3 letras, 6 dígitos e 3 caracteres alfanuméricos).


## **Regras para validação de RFCs:**

Os RFCs seguem um padrão sequencial de 4 grupos de caracteres conforme regras descritas a seguir:

**Grupo 1**

Os 3 ou 4 primeiros caracteres do devem seguir a regra abaixo:
- 3 letras se for pessoa jurídica ou 4 letras se for pessoa física.

**Grupo 2**

Os próximos 6 caracteres são para informar a data de nascimento do indivíduo ou data da criação empresa no formato yyMMdd.
- ano do nascimento ou criação (2 dígitos).
- mês do nascimento ou criação (2 dígitos).
- dia do nascimento ou criação (2 dígitos).

Exemplo: 940222 (22 de fevereiro de 1994)

**Grupo 3**

O terceiro grupo consiste de 2 caracteres alfanuméricos quaisquer. (0123456789ABCDEFGHIJKLMN&OPQRSTUVWXYZ Ñ)

**Grupo 4**

O último caracter pode ser um dígito de 0 a 9 ou a letra A.

## RFC Genérico

Caso o indivíduo ou empresa não possua um RFC, ele pode usar um RFC genérico fazer suas transações.
Abaixo estão os RFCs genéricos usados em operações para público em geral ou estrangeiros:

- Público em geral: **XAXX010101000**

- Estrangeiros: **XEXX010101000**

## **Como usar o validador**

Existe validador de RFC tanto para o backend quanto para o frontend. Eles aplicam as mesmas regras e são independentes.

**Ps.:** O RFC não é obrigatório no México, portanto, caso não esteja preenchido, ele deverá ser considerado como válido.

### **Backend**

O validador do RFC no backend se encontra na classe DocumentValidator dentro do package com.accurate.acec.validator.document que fica no projeto acecCommon.

Exemplo:
```java
String validRfc = "AALC86071721A";
validatedDocument = new ValidatedDocumentType();
validatedDocument = DocumentValidator.isValidDocumentNr(null, validRfc);
if(!validatedDocument.isValidDocument()){
    System.out.println("O " + validatedDocument.getDocumentType() + " não é válido.");
    //O RFC não é válido.
}
```

### **Frontend**

No frontend existe uma máscara e uma função Javascript que podem ser utilizadas para validar um campo do tipo RFC. 

- Máscara
	
	Para usar a máscara em um campo, pode-se adicionar o código abaixo e chamá-lo conforme exemplo.

```javascript
$('.rfc .input').inputmask({
    jitMasking: true,
    mask: "A{3,4}-999999-##U",
    positionCaretOnClick: "radixFocus",
    radixPoint: ",",
    _radixDance: true,
    nullable: false,
    placeholder: " ",
    removeMaskOnSubmit: true,
    definitions: {
        "U": {
            validator: "[aA0-9]",
            casing: "upper"
        }
    }
});

```
Exemplo:
```html
<dl class="field rfc">
    <input class="input rfc" type="text" />
</dl>
```

- Função JS

	Para realizar a validação completa, basta adicionar a função abaixo e chamá-la conforme exemplo
```javascript
// Funcao para validar RFC - feature-umx-107-RFC-Validation
		//
		function validRFC(rfc, aceptarGenerico) {

			var re = /^([A-ZÑ&]{3,4}) ?(?:- ?)?(\d{2}(?:0[1-9]|1[0-2])(?:0[1-9]|[12]\d|3[01])) ?(?:- ?)?([A-Z\d]{2})([A\d])$/;
			var validado = rfc.match(re);

			if (!validado)  //Coincide con el formato general del regex?
				return false;

			//Separar el dígito verificador del resto del RFC
			var digitoVerificador = validado.pop(),
				rfcSinDigito = validado.slice(1).join(''),
				len = rfcSinDigito.length,

				//Obtener el digito esperado
				diccionario = "0123456789ABCDEFGHIJKLMN&OPQRSTUVWXYZ Ñ",
				indice = len + 1;
			var suma,
				digitoEsperado;

			if (len == 12) suma = 0
			else suma = 481; //Ajuste para persona moral

			for (var i = 0; i < len; i++)
				suma += diccionario.indexOf(rfcSinDigito.charAt(i)) * (indice - i);
			digitoEsperado = 11 - suma % 11;
			if (digitoEsperado == 11) digitoEsperado = 0;
			else if (digitoEsperado == 10) digitoEsperado = "A";

			//El dígito verificador coincide con el esperado?
			// o es un RFC Genérico (ventas a público general)?
			if ((digitoVerificador != digitoEsperado)
				&& (!aceptarGenerico || rfcSinDigito + digitoVerificador != "XAXX010101000"))
				return false;
			else if (!aceptarGenerico && rfcSinDigito + digitoVerificador == "XEXX010101000")
				return false;
			return rfcSinDigito + digitoVerificador;
		}

```
Exemplo:
```javascript
var rfc = 'XAXX010101000';
if (!validRFC(rfc, true)) {
	$rfcField.addClass('error');
	$rfcField.find('.msg-error').text('Informe su RFC');
	return;
}
```

## **Referências**

### Exemplo Java
https://gitlab.infracommerce.com.br/sales/checkout/commit/42743d6cf119dd894d9bb383ae8406a14035e08f

### Exemplo JS
https://gitlab.infracommerce.com.br/store-unilevermx/unilevermx-front/blob/develop/htdocs_src/desktop/js/custom-customer-register.js

### Padrão RFC
http://www.oecd.org/tax/automatic-exchange/crs-implementation-and-assistance/tax-identification-numbers/Mexico-TIN.pdf

### Função JS
https://es.stackoverflow.com/questions/31713/c%C3%B3mo-validar-un-rfc-de-m%C3%A9xico-y-su-digito-verificador
