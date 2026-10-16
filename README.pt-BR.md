<div align="center">

# Your Money, Your Life

**Controle financeiro pessoal com autenticação Firebase, Firestore e gráficos interativos.**

🇺🇸 [Read in English](README.md)

[![CI](https://github.com/vallevinicius/ControleFinanceiro/actions/workflows/firebase-hosting-pull-request.yml/badge.svg)](https://github.com/vallevinicius/ControleFinanceiro/actions/workflows/firebase-hosting-pull-request.yml) ![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?logo=javascript&logoColor=white) ![Firebase](https://img.shields.io/badge/Firebase--FFCA28?logo=firebase&logoColor=white) ![Chart.js](https://img.shields.io/badge/Chart.js--FF6384?logo=chartdotjs&logoColor=white)

</div>

## Sobre

Aplicação web responsiva para registrar receitas e despesas e analisá-las por mês ou por ano. Feita com módulos JavaScript puros (sem framework) sobre Firebase Authentication e Cloud Firestore, com deploy no Firebase Hosting.

## Funcionalidades

- Cadastro, login e recuperação de senha (Firebase Auth)
- Transações gravadas por usuário no Firestore, sincronizadas entre dispositivos
- Dashboard com saldo, histórico e visões mensal/anual
- Dashboards por categoria com gráficos de coluna, barra, linha e pizza
- Layout responsivo com menu lateral recolhível e modais próprios

## Stack

| Camada | Tecnologia |
|---|---|
| Front-end | HTML5, CSS3, JavaScript (ES modules) |
| Backend | Firebase Authentication, Cloud Firestore, Firebase Hosting |
| Gráficos | Chart.js |
| CI | GitHub Actions → Firebase Hosting preview on every PR |

## Segurança

- As regras do Firestore (`firestore.rules`) só permitem que o usuário logado leia ou altere transações com o próprio `uid`
- A configuração web do Firebase em `public/main.js` é pública por design; o controle de acesso fica nas regras de segurança

## Como rodar

**Pré-requisitos:** um projeto Firebase com Authentication (e-mail/senha) e Firestore, Firebase CLI

```bash
npm install -g firebase-tools
firebase login
# coloque o firebaseConfig do seu projeto no topo de public/main.js
firebase emulators:start      # ou: firebase serve
firebase deploy               # regras, índices e hosting
```
Os índices compostos usados pelos dashboards estão em `firestore.indexes.json` e são criados pelo `firebase deploy`.

## Equipe

- [Vinicius do Valle](https://github.com/vallevinicius)
