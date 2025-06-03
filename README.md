# ENEM Quiz 

- Este repositório contém o código-fonte para o sistema de Questões ENEM, uma plataforma interativa para estudantes praticarem questões de provas anteriores do ENEM e receberem feedback imediato.


## 🚀 Tecnologias Utilizadas

### O projeto é construído com as seguintes tecnologias principais:
  - Backend (API):
      - Java: Linguagem de programação.
      - Spring Boot: Framework para desenvolvimento rápido de aplicações Java.
      - PostgreSQL: Sistema de gerenciamento de banco de dados relacional.

  - Frontend:
        Angular: Framework para construção de interfaces de usuário.

## 🏗️ Arquitetura do Projeto: Clean Architecture

O projeto adota a Clean Architecture para garantir um design desacoplado, testável e de fácil manutenção. A estrutura é organizada em camadas concêntricas, onde as dependências sempre fluem de fora para dentro:
  - **domain:** O núcleo da aplicação, contendo as entidades de negócio puras e as interfaces (portas de saída) que definem as necessidades de persistência ou comunicação externa. É independente de frameworks e bancos de dados.

  - **application:** Contém os Casos de Uso (Use Cases), que orquestram a lógica de negócio específica da aplicação. Define as interfaces (portas de entrada e saída) que as camadas externas devem implementar ou consumir.

  - **adapter:** Adapta as camadas externas (web, persistência, serviços externos) para se comunicarem com as portas definidas nas camadas application e domain. É aqui que frameworks como Spring Data JPA e controladores REST são utilizados.

  - **infrastructure:** A camada mais externa, responsável pela configuração e inicialização da aplicação, incluindo a configuração do Spring Boot e do banco de dados.

## ✨ Funcionalidades
- MVP (Produto Mínimo Viável)

- As funcionalidades iniciais focam na experiência essencial do quiz:
    - Listagem de Disciplinas: Usuários podem visualizar uma lista de disciplinas disponíveis (ex: Ciências Humanas, Matemática).

    - Início de Quiz: Seleção de uma disciplina para iniciar um quiz com questões relacionadas.

    - Resolução de Questões: Apresentação de questões com alternativas para o usuário escolher.

    - Submissão e Feedback: Após responder, o usuário recebe feedback imediato sobre a correção de sua resposta e a alternativa correta.

    - Resultados do Quiz: Ao final de um quiz, é exibido um resumo do desempenho do usuário.

 ### Funcionalidades Futuras Planejadas
  - Autenticação de Usuários: Sistema de login e cadastro para usuários.
  - Acompanhamento de Progresso: Registro e visualização do histórico de quizzes e desempenho do usuário.
  - Feedback Avançado com IA: Implementação de inteligência artificial para fornecer análises mais aprofundadas sobre as respostas dos usuários.

## 📊 Modelo de Dados
- O banco de dados PostgreSQL armazena as questões do ENEM e seus componentes. As principais entidades e seus relacionamentos são:
    disciplines: Armazena as disciplinas (ex: "Ciências Humanas e suas Tecnologias").
    questions: Contém os detalhes das questões (enunciado, ano, índice ENEM, idioma, disciplina).
    alternatives: Armazena as alternativas de cada questão.
    question_files: Guarda referências a arquivos (imagens, gráficos) associados às questões.

Relacionamentos Chave:
  - **disciplines** 1:N questions
  - **questions** 1:N alternatives
  - **questions** 1:N question_files


📄 Licença

Este projeto está licenciado sob a licença MIT License
