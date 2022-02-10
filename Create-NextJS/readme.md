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

## Também foi adicionado componente para renderizar apenas uma vez, criando um arquivo dentro da pasta pages de nome: _documents.tsx
arquivo fica configurado no server side, persistindo configurações na página para o styled component.
Link das informações do arquivo _documents.tsx: <a href="https://raw.githubusercontent.com/vercel/next.js/canary/examples/with-styled-components/pages/_document.js" target="_blank">Clique aqui</a>


### Fonte: <a href="https://github.com/vercel/next.js/tree/canary/examples/with-styled-components">link</a>
