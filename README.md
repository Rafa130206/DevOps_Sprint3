# AutoTTU API como App Service

API RESTful desenvolvida em **ASP.NET Core** para gerenciar slots, usuários e operações relacionadas funcionando na nuvem como App Service.

---

## 📌 Tecnologias

- .NET 8 / ASP.NET Core
- C# 12
- Entity Framework Core
- SQL Server
- Swagger / OpenAPI para documentação de endpoints

---

## 🚀 Funcionalidades

- Serviço de Aplicativo rodando na nuvem
- CRUD completo de Slots, Usuários e outras entidades
- Validação de dados e tratamento de erros
- Documentação automática via Swagger UI
- Suporte a status codes corretos (200, 201, 400, 404, 500)
- Exemplo de endpoints:
  - `GET /slots` → listar todos os slots
  - `GET /slots/{id}` → buscar slot por ID
  - `POST /slots` → criar novo slot
  - `PUT /slots/{id}` → atualizar slot
  - `DELETE /slots/{id}` → apagar slot

---

## ⚙️ Como subir o Projeto

### 1. Fork do Repositório:
Faça um Fork desse repositório.
### 2. Download do arquivo `deploy-autottuapi.sh`:
No novo repositório, procure pelo arquivo `deploy-autottuapi.sh`. Clique nele e depois, na direita da tela, clique no ícone com 3 pontos (...) chamado `More Actions`. Em seguida, clique em Download e salve o arquivo no seu computador. Este arquivo possui o script para criar o Seviço de Aplicativo completo.
### 3. Portal Azure:
Faça login no Portal da Microsoft Azure e abra o `Cloud Shell`.
### 4. Subir o Script:
Quando o terminal do Cloud Shell abrir, apertem em `Gerenciar Arquivos` e, em seguida, Carregar. Selecione o arquivo `deploy-autottuapi.sh`, que acabou de ser baixado.
### 5. Alterar o Script
No terminal Cloud Shell, altere para a versão clássica e abra o editor. Selecione o Script e altere a variável `GITHUB_REPO_NAME` (Linha 22) para o nome do seu repositório:
```bash
export GITHUB_REPO_NAME="<seu_usuario_github>/DevOps_Sprint3"
```
### 6. Rodar o Script:
No Cloud Shell, conceda o privilégio de execução nmo Script:
```bash
chmod +x deploy-autottuapi.sh
```
Agora execute o Script com o seguinte comando:
```bash
 ./deploy-autottuapi.sh 
```
⚠️ Ao executar a criação do banco de dados, o Cloud Shell vai pedir para confirmar o procedimento. Digite `y` e pressione `Enter`

### 7. Ativar o Github Actions:
- 7.1. Copie o código e acesse o link fornecidos pelo Cloud Shell.
- 7.2. Acesse sua conta do Github, cole o código e conceda as permissões necessárias.
- 7.3. Retorne ao Cloud Shell e pressione `y` para substituir o WorkFlow existente

### 8. Build e Deploy:
Na aba Actions do seu repositório, aguarde o build e deploy automático da aplicação. Quando estiver concluído, acesse o link abaixo.
```bash
http://autottu-api-app.azurewebsites.net/swagger/index.html
```

### 9. Testes
Utilize os seguintes JSONs para fazer testes simples:<br/>

**POST**
```bash
{
  "modelo": "Civic EXL",
  "marca": "Honda",
  "ano": 2022,
  "placa": "ABC1D23",
  "ativoChar": "s",
  "status": true,
  "fotoUrl": "https://drive.com/fotos/civic.jpg"
}
```
```bash
{
  "modelo": "Corolla Altis",
  "marca": "Toyota",
  "ano": 2020,
  "placa": "XYZ9E88",
  "ativoChar": "n",
  "status": false,
  "fotoUrl": "https://cloud.com/fotos/corolla.jpg"
}
```

<br/>

**PUT**
```bash
{
  "idMoto": 1,
  "modelo": "Civic EXL",
  "marca": "Honda",
  "ano": 2022,
  "placa": "AAA-1234",
  "ativoChar": "s",
  "status": true,
  "fotoUrl": "https://drive.com/fotos/civic.jpg"
}
```
```bash
{
  "idMoto": 2,
  "modelo": "Corolla Altis",
  "marca": "Toyota",
  "ano": 2020,
  "placa": "XYZ9E88",
  "ativoChar": "s",
  "status": true,
  "fotoUrl": "https://cloud.com/fotos/corolla.jpg"
}
```

### 9. Acessando Azure SQL Server
Ao tentar realizar o primeiro login no banco de dados criado na Azure, provavelmente vai dar um erro de IP. Bastar clicar no texto azul do próprio erro que o problema será solucionado. Então é só fazer login novamente! 



