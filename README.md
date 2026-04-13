# 🚀 Configuração de CI com GitHub Actions (Flask)

## 📌 Objetivo

Configurar um pipeline de Integração Contínua (CI) utilizando GitHub Actions em um projeto Flask.

---

## 🧠 Passo a passo

### 1. Inicializar repositório Git

```bash
git init
git add .
git commit -m "ci: pipeline inicial"
```

---

### 2. Conectar com o GitHub

```bash
git remote add origin https://github.com/Jacquelsilva/Workflow-3-.git
git branch -M main
git push -u origin main
```

---

### 3. Criar estrutura do workflow

Criar as pastas e arquivo:

```
.github/
└── workflows/
    └── ci.yml
```

---

### 4. Criar pipeline inicial

Arquivo: `.github/workflows/ci.yml`

```yaml
name: Teste CI Inicial

on: push

jobs:
  teste:
    runs-on: ubuntu-latest

    steps:
      - run: echo "CI funcionando corretamente"
```

---

### 5. Enviar para o GitHub

```bash
git add .
git commit -m "ci: pipeline inicial funcionando"
git push
```

---

### 6. Atualizar pipeline para Flask

```yaml
name: CI - Flask API

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Clonar repositório
        uses: actions/checkout@v3

      - name: Configurar Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'

      - name: Instalar dependências
        run: pip install -r requirements.txt

      - name: Verificar sintaxe
        run: python -m py_compile app.py
```

---

### 7. Criar arquivo requirements.txt

Na raiz do projeto:

```bash
echo Flask > requirements.txt
```

---

### 8. Instalar dependências

```bash
pip install -r requirements.txt
```

---

### 9. Enviar atualização

```bash
git add requirements.txt
git commit -m "fix: requirements na raiz"
git push
```

---

## ✅ Resultado

* Pipeline configurado
* Execução automática no GitHub Actions
* Instalação de dependências funcionando
* Verificação de código ativa

---
