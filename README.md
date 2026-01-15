## Cypress do Zero a Nuvem :cloud:

Neste projeto construo minha primeira automação de testes.
A 'aplicação utiizada foi a CAC - Central de Atendimento ao Cliente, utilizando **Cypress + Javascript.**

## Pré-requisitos :white_check_mark:

**Sistemas**
Antes de começar, certifique-se de que os seguintes sistemas estejam instalados em seu computador.

>[Git](https://git-scm.com/) (2.42.1 no momento da redação deste artigo)
[Node.js](https://nodejs.org/en/) (v20.13.1 no momento da redação deste artigo)
Npm (10.8.1 no momento da redação deste artigo)
[Visual Studio Code](https://code.visualstudio.com/) (v1.90.2 no momento da redação deste artigo) ou alguma outra IDE de sua preferência


:memo: Obs. 2: Ao instalar o Node.js, o npm é instalado junto. 🎉

:memo: Obs. 3: Para verificar as versões do git, Node.js e npm instaladas em seu computador, execute o comando git --version && node --version && npm --version em seu terminal de linha de comando.

:memo:Obs. 4: Deixei links para os instaladores na lista de requisitos acima, caso você ainda não os tenha instalados.

## Passo a passo

### Fork e clone do projeto 🐑

1. Abra o navegador e visite a URL https://github.com/wlsf82/cypress-do-zero-a-nuvem.
2. Faça um fork do projeto.
3. Em seu fork, clique no botão Code, escolha a opção clone via SSH e copie o link de clone do projeto.
4. Em seu terminal de linha de comando (em uma pasta onde você armazena seus projetos de software), execute o comando git clone [cole-o-link-copiado-aqui].
👨‍🏫 Para garantir que você está clonando seu fork corretamente, verifique seu nome de usuário do GitHub na URL de clone do projeto. Deve ser semelhante a git@github.com:[seu-nome de usuário-aqui]/cypress-do-zero-a-nuvem.git.

5. Após clonar o projeto, acesse o diretório recém-clonado (cd cypress-do-zero-a-nuvem/).

Obs.: Dentro do diretório cypress-do-zero-a-nuvem/, você deve ter os subdiretórios .git/ (diretório oculto), lessons/ e src/, e os arquivos .gitignore (arquivo oculto), LICENSE, package.json e README.md.

Dentro do diretório src/, você deverá ver os arquivos index.html, privacy.html, script.js e style.css. Este é o código fonte da aplicação em teste.

### Instalação e inicialização do Cypress 🌲

1. Na raiz do projeto, execute o comando npm install cypress@13.12.0 --save-dev (ou npm i cypress@13.12.0 -D para a versão curta).
2. Execute o comando npx cypress open para abrir o Cypress pela primeira vez e deixe-o guiá-lo na criação de uma suite de testes de ponta a ponta (E2E).
3. Por fim, com a Cypress App aberta, crie um arquivo chamado CAC-TAT.cy.js e feche a Cypress App.
Obs. 2: Quando iniciado pela primeira vez, o Cypress cria automaticamente o arquivo cypress.config.js e o diretório cypress/, com seus subdiretórios e2e/, fixtures/ e support/, com seus respectivos arquivos.

### Configuração extra
1. Atualize o arquivo cypress.config.js da seguinte maneira.

```const { defineConfig } = require('cypress')

module.exports = defineConfig({
  viewportHeight: 880,
  viewportWidth: 1280,
  e2e: {},
}) 
``` 

>👨‍🏫 Com a configuração acima, estamos "dizendo" ao Cypress que substituiremos as dimensões de altura e largura padrão do Cypress.

Pronto!

### Atualização de script

### Estrutura básica

1. Dentro do arquivo cypress/e2e/CAC-TAT.cy.js, adicione a seguinte estrutura básica para a suite de testes:
```
describe('Central de Atendimento ao Cliente TAT', () => {
  it('verifica o título da aplicação', () => {

  })
})
```
>👨‍🏫 O bloco describe define a suite de testes e o bloco it define o caso de teste.

2. Dentro da função de callback do bloco it, adicione o código que visita a aplicação (através do caminho relativo ./src/index.html), e verifique se seu título é Central de Atendimento ao Cliente TAT.
> 👨‍🏫 Para a verificação do título, leia sobre a funcionalidade cy.title() na documentação oficial do Cypress.

> Além disso, leia sobre a funcionalidade .should().

3. Com o teste criado, modifique a seção de scripts do arquivo package.json, conforme abaixo.
```
"scripts": {
  "cy:open": "cypress open",
  "test": "cypress run"
},
```

4. Por fim, no terminal de linha de comando, na raiz do projeto (ou no atalho do VS Code), execute o comando npm run cy:open para abrir a Cypress App e executar o novo teste em modo interativo. Siga em frente somente quando o teste estiver passando.

--------------------