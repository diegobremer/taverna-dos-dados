# ⚔️ Taverna dos Dados — Gerador de Atributos AD&D 2ª Edição

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Vanilla JS](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?logo=javascript&logoColor=black)
![Firebase](https://img.shields.io/badge/Firebase-Firestore-FFCA28?logo=firebase&logoColor=black)

Uma aplicação web imersiva desenvolvida para automatizar a rolagem de atributos (3d6) de personagens para o sistema clássico de RPG **Advanced Dungeons & Dragons (AD&D) 2ª Edição**. 

O projeto não apenas simula a rolagem física dos dados com animações, mas também calcula automaticamente as raças elegíveis com base nos atributos gerados e salva o histórico de todos os heróis em tempo real.

🔗 **[Acessar a Taverna dos Dados](https://diegobremer.github.io/taverna-dos-dados/)**

---

## ✨ Funcionalidades

* **Rolagem de Dados (3d6):** Geração de números aleatórios de 3 a 18 para os seis atributos clássicos (Força, Destreza, Constituição, Inteligência, Sabedoria e Carisma).
* **Análise de Elegibilidade de Raça:** Lógica baseada nas regras do Livro do Jogador de AD&D 2ª Ed para habilitar ou desabilitar raças (Humano, Anão, Elfo, Gnomo, Meio-Elfo, Halfling) de acordo com os atributos mínimos e máximos exigidos.
* **Cálculo de Ajustes Raciais:** Modal interativo que demonstra o "antes e depois" dos atributos ao selecionar uma raça, aplicando bônus e penalidades automaticamente.
* **Crônica dos Aventureiros (Tempo Real):** Sincronização em tempo real de todas as rolagens feitas pelos usuários utilizando WebSocket via Firebase.
* **Painel de Mestre (Admin):** Sistema de exclusão individual ou limpeza total do banco de dados protegido por senha de validação.

---

## 🛠️ Tecnologias Utilizadas

O projeto foi construído sem o uso de frameworks complexos no front-end, focando no domínio de linguagens fundamentais e integração com serviços de Cloud:

* **HTML5 & CSS3:** Interface responsiva, com uso intensivo de `CSS Grid`, `Flexbox`, propriedades customizadas (Variáveis CSS) e animações (`@keyframes`).
* **JavaScript (ES6+):** Lógica assíncrona (`async/await`), manipulação de DOM, Módulos (`import/export`) e validações de formulário.
* **Firebase (Cloud Firestore):** Banco de dados NoSQL orientado a documentos para persistência e distribuição dos dados em tempo real (`onSnapshot`).

---

## 🔒 Arquitetura e Segurança (Cloud)

Para garantir a integridade da aplicação e evitar o esgotamento da cota de requisições do Firebase, as seguintes práticas de segurança em nuvem foram implementadas:

1. **API Key Restrictions (Google Cloud Console):** A chave de comunicação com o Firebase possui restrição de referenciador HTTP, operando exclusivamente sob o domínio autorizado (`github.io`).
2. **Firebase Security Rules:** O banco de dados foi blindado através de regras granulares (`allow create`, `allow read`), permitindo que a aplicação consuma e gere dados, mas validando permissões de exclusão e bloqueando edições de registros passados (`allow update: if false`).

---

## 🚀 Como rodar o projeto localmente

Por ser uma aplicação baseada em Client-Side Rendering (CSR) puro com Backend as a Service (BaaS), rodar o projeto é extremamente simples:

1. Clone o repositório:
    ```bash
    git clone https://github.com/diegobremer/taverna-dos-dados.git
    ```
2. Abra a pasta do projeto e inicie um servidor local. Se estiver usando o VS Code, você pode usar a extensão **Live Server**.
3. A aplicação estará disponível em `http://localhost:5500` (ou porta configurada).

---

## 👨‍💻 Autor

**Diego Bremer** *Estudante de Engenharia de Software*

🔗 [LinkedIn](https://www.linkedin.com/in/diegobremer-dev) | 🐙 [GitHub](https://github.com/diegobremer)
