# Aplicação NodeJS utilizando o express


## Pacotes básicos para instalação

```
npm i --save pm2 && sudo npm i --save -g pm2
npm i --save-dev nodemon && sudo npm i -g nodemon
npm i --save body-parser
```

## comandos básicos para o pm2

```
pm2 monit
pm2 status
pm2 show 0
pm2 restart
pm2 restart nome-do-app
pm2 stop 0
pm2 kill
```

## Usando expressões do express

### Importando módulos do express

```
const express = require("express");
```

### Chamado express

```
const app = express();
```

## Detalhes básicos sobre Express

- Express trabalha com padrão chain of responsibility;
- Função middleware recebe req (requisição), res (resposta) e next (chamada para próxima função);
- Next é chamado quando é necessário chamar uma outra função dentro da própria requisição da mesma URL;

### Qualquer url será direcionada para a requisição abaixo

```
app.use((req, res) => {
  res.send("estou bem");
});
```

### Através do acesso a URL test trará uma resposta json

```
app.get("/test", (req, res) => {
  res.json({ nome: "jorge" });
});
```

### Recebendo uma requisição pelo id

```
app.get("/clientes/:id", (req, res, next) => {
  res.send(`Cliente: ${req.params.id} foi selecionado`);
});
```

### Recebendo uma requisição tipo query

- chamada: http://localhost:port/clientes/relatorio?completo=true&ano=2018

```
app.get("/clientes/relatorio", (req, res, next) => {
  res.send(`Cliente relatório completo: ${req.query.completo}, ano: ${req.query.ano}`);
});
```

<b>Obs.:</b> Os middleware respeitam a ordem de chamada do algoritmo. Funções mais específicas ficam acima das genéricas.

### Usando o body-parser

#### Chamado body-parser - utilizando chamada no body com json

```
app.use(bodyParser.json());
```

#### Também pode ser chamado qualquer texto

```
app.use(bodyParser.text());
```

#### Também pode ser chamado qualquer dado urlencoded - muito usado no front-end para envio de formulários

```
app.use(bodyParser.urlencoded({extended: true}));
```

#### Usando um middleware para uso do body-parser

- Recebe qualquer coisa no body em formato JSON

```
app.post("/corpo", (req, res) => {
  res.send(req.body);
});
```

### Escutando o backend através da porta 3001

```
app.listen(3001, () => {
console.log("backend executando");
});
```
