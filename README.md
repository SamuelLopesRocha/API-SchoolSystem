📚 API Escola – Alunos, Professores e Turmas
Esta API foi desenvolvida em Python utilizando o framework Flask com o objetivo de simular o gerenciamento de uma escola, contendo três entidades principais: Aluno, Professor e Turma. A aplicação segue a arquitetura MVC, possui banco de dados SQLite, documentação via Swagger, testes automatizados com TDD e está pronta para containerização com Docker.

🛠 Tecnologias Utilizadas
Python

Flask

Flask SQLAlchemy

Flask CORS

Swagger (Flasgger)

SQLite

Docker

TDD (Test Driven Development)

Estrutura MVC

▶️ Como Executar a API Localmente
Crie e ative o ambiente virtual:

no git bash copie os seguintes codigos:
python -m venv venv
./venv/Scripts/Activate  # No Windows
source venv/bin/activate # No Linux/macOS

Instale as dependências:
pip install flask
pip install requests

Execute o projeto:
python app.py

🐳 Executando com Docker
Crie a imagem:
docker build -t api-escolar .

Rode o container:
docker run -d -p 5000:5000 api-escolar

📄 Documentação Swagger
Acesse a documentação interativa através de:
http://localhost:5000/apidocs/

🔄 Estrutura de Endpoints

📘 Alunos
✅ POST /alunos
Exemplo de entrada:
{
  "idade": 18,
  "nome": "João da Silva",
  "observacoes": "Aluno dedicado"
}
Resposta esperada:
{
  "mensagem": "Aluno criado com sucesso!"
}

🔄 PUT /alunos/1
Exemplo de entrada:
{
  "idade": 19,
  "nome": "João Pedro da Silva",
  "observacoes": "Atualizado"
}
Resposta esperada:
{
  "mensagem": "Aluno ATUALIZADO com sucesso!"
}

📥 GET /alunos
Retorna todos os alunos.

📥 GET /alunos/1
Retorna um aluno específico pelo ID.

❌ DELETE /alunos/1
Resposta esperada:
{
  "mensagem": "Aluno DELETADO com sucesso!"
}

🧑‍🏫 Professores
✅ POST /professores
Exemplo de entrada:
{
  "idade": 20,
  "materia": "matematica",
  "nome": "Alberto",
  "observacoes": "Professor da tarde"
}
Resposta esperada:
{
  "mensagem": "Professor criado com sucesso!"
}

🔄 PUT /professores/1
{
  "idade": 20,
  "materia": "hISTORIA",
  "nome": "Alberto",
  "observacoes": "Professor da NOITE"
}
Resposta esperada:
{
  "mensagem": "Professor ATUALIZADO com sucesso!"
}

📥 GET /professores
Retorna todos os professores.

📥 GET /professores/1
Retorna um professor específico pelo ID.

❌ DELETE /professores/1
Resposta esperada:
{
  "mensagem": "Professor DELETADO com sucesso!"
}

🏫 Turmas
⚠️ A criação de uma turma exige que a API de reserva de salas esteja funcionando corretamente, pois depende de professor_id e sala_id.

✅ POST /turmas
Exemplo de entrada:
{
  "ativo": true,
  "descricao": "6º ano A - Tarde",
  "professor_id": 1,
  "sala_id": 1,
  "turma_id": 1
}
Resposta esperada:
{
  "mensagem": "Turma criada com sucesso!"
}

🔄 PUT /turmas/1
{
  "ativo": false,
  "descricao": "TURMA ENCERRADA",
  "professor_id": 1,
  "sala_id": 1,
  "turma_id": 1
}
Resposta esperada:
{
  "mensagem": "Turma ATUALIZADA com sucesso!"
}

📥 GET /turmas
Retorna todas as turmas.

📥 GET /turmas/1
Retorna uma turma específica pelo ID.

❌ DELETE /turmas/1
Resposta esperada:
{
  "mensagem": "Turma DELETADA com sucesso!"
}

📁 Organização do Projeto (MVC)
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
Esse projeto é ideal para praticar e aplicar conceitos de API RESTful, TDD, Flask e organização de projetos com boas práticas. A API está modularizada e pronta para evoluções futuras como autenticação, integração com banco de dados PostgreSQL, deploy em nuvem e muito mais!
