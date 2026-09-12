# DevShowcase API

Backend REST da plataforma DevShowcase, desenvolvido com Python 3.11, FastAPI, SQLAlchemy e SQLite. A aplicação modela perfis de desenvolvedores, projetos, tecnologias e feedbacks com persistência relacional.

## Executar localmente

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

A documentação interativa fica disponível em `http://localhost:8000/docs`.

## Testes

```bash
pytest -q
```

## Modelo relacional

- `Profile 1:N Project`: um perfil pode possuir diversos projetos.
- `Project N:N Technology`: projetos e tecnologias são associados pela tabela `project_technology`.
- `Project 1:N Feedback`: cada projeto pode receber diversas opiniões.

## Endpoints

| Método | Rota | Finalidade |
|---|---|---|
| POST | `/api/profiles` | Cadastrar perfil com URLs validadas |
| GET | `/api/profiles/{id}` | Buscar perfil por identificador |
| POST | `/api/technologies` | Cadastrar tecnologia |
| GET | `/api/technologies` | Listar tecnologias |
| POST | `/api/projects` | Cadastrar projeto e associar tecnologias |
| GET | `/api/projects` | Listar projetos |

## Licença

MIT
