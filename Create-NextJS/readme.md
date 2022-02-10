# Criando projeto NextJS + Typescript + styled-components

## Iniciando projeto:

npx create-next-app app-name --typescript

## Instalando styled-componentes

```
npm i styled-components
npm i @types/styled-components
```

## Instalando dependências babel para executar o styled-components

```
npm i babel-preset-next
npm install --save -D babel-plugin-styled-components
```

## É necessário criar um arquivo na raiz do projeto de nome: .babelrc
conteúdo:

```
{
    "presets": ["next/babel"],
    "plugins": [["styled-components", { "ssr": true }]]
}
```
