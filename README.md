*Sistema de Gestão Acadêmica*

Este projeto é uma **API REST** desenvolvida como parte da **Atividade Prática Supervisionada (APS)**.  
O objetivo é criar o backend de um sistema escolar responsável por gerenciar **cursos técnicos** e **alunos**.

A aplicação não possui interface gráfica, funcionando apenas como serviço de dados para futuras aplicações web ou mobile.

---

*Tecnologias e Ferramentas*

- **Linguagem:** Java (JDK 17 ou superior)
- **Framework:** Spring Boot 3.x
- **Banco de Dados:** H2 Database (em memória)
- **Gerenciador de Dependências:** Maven
- **Testes da API:** Postman ou Insomnia

---

*Estrutura do Projeto (Padrão MVC)*

O projeto foi organizado em pacotes para facilitar a manutenção e o entendimento do código:

- **model**  
  Contém as entidades JPA que representam as tabelas do banco de dados (`Curso` e `Aluno`).

- **repository**  
  Interfaces responsáveis pela comunicação com o banco de dados usando Spring Data JPA.

- **controller**  
  Camada responsável por expor os endpoints REST e tratar as requisições HTTP.

---

*Funcionalidades da API*

*Gerenciamento de Cursos (`/api/cursos`)*

- **POST** – Cadastrar um novo curso  
- **GET** – Listar todos os cursos cadastrados  
- **GET /{id}** – Buscar detalhes de um curso específico  
- **DELETE /{id}** – Remover um curso (somente se não houver alunos vinculados)

---

 *Gerenciamento de Alunos (`/api/alunos`)*

- **POST** – Matricular um aluno vinculando-o a um curso existente  
- **GET** – Listar todos os alunos  
- **GET /{id}** – Buscar um aluno específico  
- **PUT /{id}** – Atualizar dados do aluno (ex: e-mail)  
- **DELETE /{id}** – Cancelar matrícula (remover aluno)

---

 *Relacionamento entre Entidades*

- Um **Curso** pode ter vários **Alunos**
- Um **Aluno** pertence a apenas um **Curso**
- Não é permitido excluir um curso que possua alunos cadastrados

---

 *Testes da API*

Os testes foram realizados utilizando **Postman** ou **Insomnia**, enviando requisições HTTP no formato **JSON**.

 *Banco de Dados*

O sistema utiliza o **H2 Database**, um banco de dados leve e em memória, ideal para projetos acadêmicos.
