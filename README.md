# HarmonyWork - API (Global Solution 2025)

API desenvolvida para a disciplina de Software Development C# com o tema "O Futuro do Trabalho". O HarmonyWork é uma solução de organização inteligente que gerencia tarefas baseando-se não apenas em prazos, mas na energia mental necessária para realizá-las.

## Desenho de Solução
<img width="681" height="621" alt="FluxogramaAPI drawio" src="https://github.com/user-attachments/assets/37136927-44dc-4a37-bb87-a66b70512a9c" />


## Integrantes do Grupo
* Bruno Venturi Lopes Vieira - 99431
* Guilherme Alves de Lima - 550433
* Leonardo de Oliveira Ruiz - 98901

## Link Video YT
https://youtu.be/EGwowtuvVcc

## Tecnologias Utilizadas
* .NET (ASP.NET Core Web API)
* C#
* Entity Framework Core (Abordagem Code First)
* SQL Server
* Swashbuckle (Swagger UI para documentação)
* Asp.Versioning (Controle de versão da API)

## Arquitetura e Padrões
O projeto segue uma arquitetura modular para garantir a escalabilidade e a separação de responsabilidades, conforme as boas práticas de desenvolvimento:

* Controllers: Responsáveis apenas por receber as requisições HTTP e retornar os Status Codes adequados.
* Services: Camada onde reside a regra de negócio e a comunicação com o banco de dados.
* DTOs (Data Transfer Objects): Objetos utilizados para filtrar dados de entrada e saída, protegendo a integridade das entidades do banco.
* Models: Classes que representam as tabelas do banco de dados.
* Versionamento: A API foi estruturada para suportar múltiplas versões, acessível via rota /api/v1/.

## Funcionalidades
1. CRUD Completo de Tarefas (Criar, Ler, Atualizar, Deletar).
2. Classificação de Tarefas por Nível de Energia (Baixa, Média, Alta).
3. Status de processamento (Pendente, Em Progresso, Concluída).
4. Documentação automática via Swagger.

## Pré-requisitos
* .NET SDK instalado.
* SQL Server ou LocalDB configurado.
* Visual Studio 2022 ou superior.

## Como Executar o Projeto

1. Configuração do Banco de Dados:
   Verifique a string de conexão "DefaultConnection" no arquivo appsettings.json. Por padrão, está configurada para usar o (localdb)\mssqllocaldb.

2. Aplicação das Migrations:
   Abra o terminal na pasta raiz do projeto (ou use o Console do Gerenciador de Pacotes no Visual Studio) e execute o comando abaixo para criar o banco de dados:
   dotnet ef database update

3. Execução:
   Execute o projeto pelo Visual Studio (F5) ou via terminal com o comando:
   dotnet run

4. Acesso à Documentação:
   Após iniciar, acesse o endereço abaixo no navegador para visualizar e testar os endpoints:
   https://localhost:7167/swagger (A porta pode variar dependendo da sua configuração local).

## Endpoints Principais (v1)

* GET /api/v1/tarefas
  Retorna a lista de todas as tarefas cadastradas.

* POST /api/v1/tarefas
  Cria uma nova tarefa.
  Corpo da requisição (JSON): Título, Descrição, Data de Vencimento e Energia Necessária.

* PUT /api/v1/tarefas/{id}
  Atualiza os dados de uma tarefa existente.

* DELETE /api/v1/tarefas/{id}
  Remove uma tarefa do sistema.
