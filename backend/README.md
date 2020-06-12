# MasterClass #07

## TypeScript, o início, de forma pratica

### Passo a Passo - Backend

Para iniciar o projeto:<br />
`yarn init -y` ou `npm init -y`<br />

Adicionando o TypeScript como dependencia de desenvolvimento:<br />
`yarn add -D typescript`<br />

Criando um servidor:<br />
`yarn add express`<br />

Criar uma pasta src e um arquivo index.ts dentro da pasta src criada.<br />

Adicionando a tipagem do express como dependencia de desenvolvimento: <br />
`yarn add @types/express -D`<br />

Convertendo o typeScript para javaScript<br />
`yarn tsc --init`<br />
Ao executar o comando acima é criado o arquivo {...} tsconfig.json<br />
Abra esse arquivo tsconfig.json e altere a propriedade:<br />
`// "outDir": "./", /* Redirect output structure to the directory. */`<br />
para<br />
`"outDir": "./dist", /* Redirect output structure to the directory. */`<br />
agora para gerar o javaScript da sua aplicação basta executar o comando:<br />
`yarn tsc`<br />
e então dentro da pasta dist que você configurou no arquivo tsconfig.json estará o arquivo tranpilado para javaScript.<br />

Agora para automatizar esse processo de transpilação de codigo iremos utilizar uma lib chamada ts-node-dev então execute o comando abaixo:<br />
`yarn add ts-node-dev -D`<br />

Agora para levantar o servidor basta executar o comando: <br />
`yarn ts-node-dev --respawn --transpileOnly src/index.ts`

Podemos simplificar esse comando abrindo o arquivo package.json e adicionando o script abaixo:<br />
`"scripts": { "dev:server": "ts-node-dev --respawn --transpileOnly src/index.ts" },`<br />

Agora para levantar o servidor basta executar o comando:<br />
`yarn dev:server`<br />

Agora precisamos configurar o cors para saber quais url's podem acessar nosso
backend. Então execute o comando:<br />
`yarn add cors`<br />
`yarn add @types/cors`<br />

Observação: Depois que o projeto estiver ok, podemos executar:<br />
`yarn tsc`<br />
Então tudo será convertido para javaScript dentro da pasta dist.
Então podemos também rodar o projeto com o comando:<br />
`node dist/index.js`<br />
E podemos acessar nosso backend no endereço:<br />
`http://localhost:3333/users`
