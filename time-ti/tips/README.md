# Tips para os Alunos

## Objetivo
Sugestão para a estrutura do projeto:

- `Poetry` para controle de dependencias e ambiente virtual;
- `.env` para variaveis de ambiente, incluindo a chave do Gemini;
- `poetry run` para executar o projeto no ambiente correto.

## 1. Instalar o Poetry

Se o Poetry ainda nao estiver instalado na maquina, use um dos caminhos abaixo.

### macOS com Homebrew

```bash
brew install poetry
```

### macOS ou Linux com instalador oficial

```bash
curl -sSL https://install.python-poetry.org | python3 -
```

### Windows com PowerShell

```powershell
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
```

Depois, confirme:

```bash
poetry --version
```

## 2. Entrar na pasta do projeto

### macOS ou Linux

```bash
cd /caminho/para/time-ti
```

### Windows

```powershell
cd C:\caminho\para\time-ti
```

## 3. Configurar o ambiente virtual dentro do projeto

Esse projeto foi preparado para manter o ambiente virtual na pasta `.venv`.

```bash
poetry config virtualenvs.in-project true
```

## 4. Instalar as dependencias

Com o Poetry configurado, instale tudo a partir do `pyproject.toml` e do `poetry.lock`:

```bash
poetry install
```

## 5. Criar o arquivo .env

Existe um arquivo modelo chamado `.env.example`.

Crie o `.env` a partir dele:

### macOS ou Linux

```bash
cp .env.example .env
```

### Windows PowerShell

```powershell
Copy-Item .env.example .env
```

### Windows Prompt de Comando

```cmd
copy .env.example .env
```

Depois edite o arquivo `.env` e preencha a chave:

```env
POETRY_VIRTUALENVS_IN_PROJECT=true
GEMINI_API_KEY=sua_chave_aqui
```

Observacoes:

- nao compartilhe a chave com outras pessoas;
- nao suba o `.env` para o Git;
- o projeto ja le o `.env` automaticamente ao iniciar.

## 6. Como rodar o projeto

### Gerar o relatorio

### macOS, Linux ou Windows

```bash
poetry run python main.py
```

Esse comando gera ou atualiza o arquivo:

- `relatorio_falhas.md`

### Rodar os testes

### macOS, Linux ou Windows

```bash
poetry run python -m unittest discover -s tests -v
```

## 7. Fluxo recomendado para os alunos

Siga esta sequencia:

1. instalar o Poetry;
2. entrar na pasta do projeto;
3. rodar `poetry config virtualenvs.in-project true`;
4. rodar `poetry install`;
5. criar `.env` com base no `.env.example`;
6. preencher `GEMINI_API_KEY`;
7. rodar `poetry run python main.py`.

## 8. Erros comuns

### `ModuleNotFoundError: No module named 'pandas'`
Voce provavelmente executou:

```bash
python3 main.py
```

Use:

```bash
poetry run python main.py
```

No Windows, o comando e o mesmo:

```powershell
poetry run python main.py
```

### O projeto nao usa a chave do `.env`
Confira se:

- o arquivo se chama exatamente `.env`;
- a chave esta preenchida em `GEMINI_API_KEY`;
- voce esta rodando o projeto pela pasta raiz do repositorio.

### O Gemini falhou, mas o relatorio foi gerado
Isso e esperado quando:

- a chave esta invalida;
- a internet falhou;
- a API do Gemini nao respondeu.

Nesses casos, o projeto usa o resumo local como fallback e continua gerando o relatorio.
