# 📘 <Descompila> — MVP

O **Descompila** é um sistema inicial para gerenciamento e resolução de dúvidas acadêmicas, desenvolvido para a disciplina **Gerenciamento de Projeto de Software**.  
O MVP valida o fluxo básico entre **aluno → dúvida → professor → resposta**, servindo como base para evolução futura.

---

## 🎯 Objetivo do MVP

- Validar a proposta central do projeto.  
- Permitir que alunos enviem dúvidas por meio de um formulário simples.  
- Permitir que professores visualizem, filtrem e respondam dúvidas.  
- Criar um fluxo funcional mínimo para coleta de feedback real.  

---

## 🚀 Funcionalidades Implementadas

### 🔹 1. Login (Professor)
- Login via **email e senha**.
- Validação via Firestore.
- Senha armazenada usando **hash SHA-256**.
- Criação de sessão com token básico no navegador.
- Redirecionamento automático para o dashboard.

---

### 🔹 2. Dashboard do Professor
- Separação das dúvidas em:
  - **Pendentes**
  - **Respondidas**
- Listagem de perguntas com:
  - título  
  - descrição  
  - disciplina  
  - data formatada  
  - status  
- Visualização de respostas associadas.
- Campo para **enviar resposta diretamente no dashboard**.
- Atualização do status para “respondida”.

---

### 🔹 3. Criação de Dúvidas (Aluno)
- Formulário contendo:
  - título  
  - descrição  
  - disciplina  
- Envio direto ao Firestore.
- Uso de `Timestamp.now()` para data/hora.
- Campo **answered = false** criado automaticamente.

---

### 🔹 4. Listagem de Dúvidas (Aluno)
- Exibe todas as questões cadastradas.
- Botão para visualizar respostas.
- Botão para abrir a tela de criação.
- Datas exibidas no formato:  
  **7 de dezembro de 2025 às 14:32**

---

## 🏗️ Arquitetura do MVP

### Frontend
- HTML, CSS e JavaScript puro.
- Módulos ES6 (`type="module"`).
- Sem frameworks para manter simplicidade.

### Backend
- Firebase:
  - **Firestore Database** (dados principais)
  - Estrutura:
    ```
    questoes/
      {id}/
        title
        description
        discipline
        created_at
        answered
        respostas/
          {id}/
            text
            created_at
    Professor/
      {id}/
        name
        email
        password (SHA-256)
    ```

---
