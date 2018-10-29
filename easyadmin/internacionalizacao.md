# Internacionalização

Este documento contém informações de como efetuar a internacionalização do Easy Admin.

## Adicionando suporte a internacionalização

Por padrão, caso o modulo seja iniciado tendo como base o projeto `module-example`, ele já virá com suporte a internacionalização ativo.

Caso precise adicionar o suporte a internacionalização a um novo módulo:

*  Verifique se no arquivo `package.json` estão presentes as seguintes dependências, caso não estejam adicione e rode o comando `npm install`:

```javascript
{
    devDependencies: {
        "i18n-webpack-plugin": "1.0.0",
        "i18n-webpack-plugin-generate-json": "git+https://gitlab.infracommerce.com.br/external-projects/i18n-webpack-plugin-generate-json.git",
    }
}
```

*  Na propriedade `scripts` do `package.json`, verifique se existe o item `i18n-generate`, caso não exista, adicione:

```javascript
{
    scripts: {
        "i18n-generate": "i18n-generate -d src/js -o src/languages -l 'en-en es-mx'"
    }
}
```

No parâmetro `-l` são informadas as linguagens que, além do português, o módulo terá suporte. Nesse exemplo, o módulo teria suporte a português, inglês e espanhol. 

*  Verifique se na pasta config, existe o arquivo `languages.js`. Este arquivo importa para o projeto os arquivos de tradução com as strings para realizar o replace. Caso não exista, crie seguindo o modelo:

```javascript
import Path from 'path';

const languages = {
	'pt-br': null, // Linguagem padrão, não precisa ser importada
	'en-en': require(Path.resolve('./src/languages/en-en.json')), // Importa inglês
	'es-mx': require(Path.resolve('./src/languages/es-mx.json')) // Importa espanhol
};
export default languages;
```
A chave o objeto deve ser o código da linguagem.

[Exemplo](https://gitlab.infracommerce.com.br/easy-management/module-example/blob/master/config/languages.js).

*  No arquivo `config/config.js`, verifique se o arquivo `languages.js` está sendo importado:

```javascript
import languages from './languages.js';
```

* Habilite a internacionalização: 

```javascript
Config.languagesSupport = true;
Config.languages = languages;
```

[Exemplo](https://gitlab.infracommerce.com.br/easy-management/module-example/blob/master/config/config.js).

*  Adicione o módulo no array `folders` do arquivo [run-i18n-generate.sh](https://gitlab.infracommerce.com.br/easy-management/structure-base/blob/master/run-i18n-generate.sh).

## Adicionando uma nova linguagem

Para adicionar uma nova linguagem, precisa alterar 2 arquivos:

*  `package.json`: Altere  script `i18n-generate`, adicionado o código da nova linguagem:
*  `config/languages.js`: Faça a importação da nova linguagem.

## Adicionando função de replace

Para o correto funcionamento da funcionalidade de internacionalização, todos textos devem ser encapsulados pela função de replace do plugin de [i18n](https://github.com/webpack-contrib/i18n-webpack-plugin). 

Durante a compilação o webpack fará a substituição da chamada da função pelo texto da tradução.

A função de replace se chama __ (2 underlines).

**Exemplos de utilização:**

Dentro de tags HTML.
```html
<strong>{__('Categorias')}</strong>
```

Como parâmetro ou propriedade:
```js
window.infrashop.utils.modal({
	header: __('Status do banner alterado com sucesso.')
}).show();
```

### Template literals / Template strings (variáveis)

O plugin atualmente não oferece suporte a template literals, então não é possível utilizar variáveis javascript dentro do texto a ser traduzido.

Para possibilitar a inserção de valores dinâmicos dentro do texto, podem ser inseridas chaves para depois realizar o replace da chave pelo valor correto.

**Exemplo de utilizaçao:**

```js
__('A posição *POSITION* não existe.').replace('*POSITION*', '[NOME DA POSIÇÃO]')
```

## Gerando arquivos para tradução

Para atualizar os arquivos de tradução basta executar o script [run-i18n-generate.sh](https://gitlab.infracommerce.com.br/easy-management/structure-base/blob/master/run-i18n-generate.sh)

```sh
sh run-i18n-generate.sh
```

1. O script atualiza o projeto [translate](https://gitlab.infracommerce.com.br/easy-management/translate), para obter os arquivos de tradução atualizados, e efetua a cópia para a pasta do respectivo projeto.

2. Após são gerados novos arquivos de linguagem, adicionando as novas string que possam ter sido adicionadas no projeto, e ainda não estejam presente nos arquivos de tradução enviados pelo tradutor.

3. Para finalizar o script efetua a cópia dos novos arquivos de linguagem para dentro do projeto *translate*. Se novas strings foram adicionadas, basta efetuar o commit das alterações dentro do projeto *translate*.

Os arquivos de tradução são gerados dentro da pasta *src/languages* de cada projeto.

Quando um novo módulo for criado, é preciso também lembrar de atualizar o script.

## Configuração

É possível configurar a geração dos arquivos de tradução alterado o script *i18n-generate* no *package.json* do projeto.

Foi criado um *fork* do plugin *[i18n-webpack-plugin-generate-json](https://github.com/mattcolman/i18n-webpack-plugin-generate-json)* onde foram realizadas algumas alterações para adequar às necessidades do Easy Admin.

Link do projeto: https://gitlab.infracommerce.com.br/external-projects/i18n-webpack-plugin-generate-json