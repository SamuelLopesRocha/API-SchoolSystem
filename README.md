## 📚 API Escola – Alunos, Professores e Turmas

Esta API foi desenvolvida em **Python** utilizando o framework **Flask** com o objetivo de simular o gerenciamento de uma escola, contendo três entidades principais: **Aluno**, **Professor** e **Turma**.

A aplicação segue a arquitetura **MVC**, utiliza **SQLite** como banco de dados, possui **documentação via Swagger**, **testes automatizados com TDD** e está **pronta para containerização com Docker**.

---

## 🛠 Tecnologias Utilizadas

- Python
- Flask
- Flask SQLAlchemy
- Flask CORS
- Swagger (Flasgger)
- SQLite
- Docker
- TDD (Test Driven Development)
- Estrutura MVC

---

## ▶️ Como Executar a API Localmente

1. **Crie e ative o ambiente virtual**

   No Git Bash ou terminal:

   ```bash
   python -m venv venv

   # Windows:
   ./venv/Scripts/Activate

   # Linux/macOS:
   source venv/bin/activate

Instale as dependências
pip install -r requirements.txt

🐳 Executando com Docker

Crie a imagem Docker: 
docker build -t api-escolar

Rode o container
docker run -d -p 5000:5000 api-escolar

📄 Documentação Swagger
Acesse a documentação interativa em:

👉 http://localhost:5000/apidocs/

## 🔄 Estrutura de Endpoints

### 📘 Alunos

**POST** `/alunos`

```json
{
  "idade": 18,
  "nome": "João da Silva",
  "observacoes": "Aluno dedicado"
}

PUT /alunos/1
{
  "idade": 19,
  "nome": "João Pedro da Silva",
  "observacoes": "Atualizado"
}

GET /alunos
Retorna todos os alunos.

GET /alunos/1
Retorna um aluno específico.

DELETE /alunos/1
{
  "mensagem": "Aluno DELETADO com sucesso!"
}

🧑‍🏫 Professores
POST /professores
{
  "idade": 20,
  "materia": "matematica",
  "nome": "Alberto",
  "observacoes": "Professor da tarde"
}

PUT /professores/1
{
  "idade": 20,
  "materia": "historia",
  "nome": "Alberto",
  "observacoes": "Professor da noite"
}

GET /professores
Retorna todos os professores.

GET /professores/1
Retorna um professor específico.

DELETE /professores/1
{
  "mensagem": "Professor DELETADO com sucesso!"
}

🏫 Turmas
⚠️ A criação de uma turma exige que a API de reserva de salas esteja funcionando corretamente (dependência de professor_id e sala_id).

POST /turmas
{
  "ativo": true,
  "descricao": "6º ano A - Tarde",
  "professor_id": 1,
  "sala_id": 1,
  "turma_id": 1
}

PUT /turmas/1
{
  "ativo": false,
  "descricao": "TURMA ENCERRADA",
  "professor_id": 1,
  "sala_id": 1,
  "turma_id": 1
}

GET /turmas
Retorna todas as turmas.

GET /turmas/1
Retorna uma turma específica.

DELETE /turmas/1
{
  "mensagem": "Turma DELETADA com sucesso!"
}

📁 Organização do Projeto (Arquitetura MVC)

├── app.py
├── alunos/
│   ├── alunos_model.py
│   ├── alunos_route.py
│   └── alunos_controller.py
├── professores/
│   ├── professores_model.py
│   ├── professores_route.py
│   └── professores_controller.py
├── turmas/
│   ├── turmas_model.py
│   ├── turmas_route.py
│   └── turmas_controller.py
├── config/
│   ├── __init__.py
│   └── database.py
├── swagger/
│   └── swagger_config.py
├── tests/
│   ├── test_alunos.py
│   ├── test_professores.py
│   └── test_turmas.py
├── Dockerfile
└── requirements.txt

✅ Conclusão
Esse projeto é ideal para praticar e aplicar conceitos como:

APIs RESTful com Flask

Arquitetura limpa (MVC)

Testes automatizados com TDD

Integração com Swagger

Docker e containerização

A API está modularizada e pronta para evoluções futuras, como autenticação, PostgreSQL, deploy em nuvem e muito mais 🚀
A API está modularizada e pronta para evoluções futuras, como autenticação, PostgreSQL, deploy em nuvem e muito mais 🚀
