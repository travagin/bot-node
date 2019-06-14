# Nodejs Project Bot
API desenvolvida para troca de mensagens com usuário e bot do sistema. 

### Installing
Baixar este repositório na sua máquina

```
npm install
node main.js
```
## Code Review

* **Arquivo Main** : Script responsável por manipular o método bootstrap da Classe Server e orientar a manipulação de erros
ser houver falha. 
  O método bootstrap criado na Classe Server, recebe um array de Routers possibilitando a extensão da API
para outros recursos.

**main.js**
```
server.bootstrap([
    bots_router.bootsRouter,
    messages_router.messagesRouter
]).then(server => {
    console.log('Servidor escutando em:', server.application.address())
}).catch(error => {
    console.log('Falha ao iniciar o servidor')
    console.error(error)
    process.exit(1)
})
```
