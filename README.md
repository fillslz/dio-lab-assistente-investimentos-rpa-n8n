# Desafio de Projeto: Assistente de Investimentos com RPA e n8n (Bootcamp Santander)
## 📌 Descrição da Solução
Neste projeto, desenvolvi um pipeline automatizado de ponta a ponta que simula um assistente de investimentos para clientes bancários, integrando técnicas de RPA (Robotic Process Automation) em Python com orquestração de workflows no n8n.
## ⚙️ Arquitetura e Fluxo do Projeto
1. **Extração e Coleta (RPA em Python):**
   - Utilizei `BeautifulSoup` e `requests` para raspar os dados da tabela de clientes da página web oficial do desafio (nome, e-mail, saldo e perfil de investidor).
   - Os dados coletados foram estruturados em formato JSON e enviados via requisição HTTP POST para o endpoint de Webhook do n8n.
2. **Orquestração e Processamento (n8n):**
   - **Webhook:** Nó configurado para receber o payload de clientes do script Python.
   - **Carga de Dados:** O n8n consome a base de produtos de investimento (`data.csv`) diretamente do GitHub Pages via nó HTTP Request e faz a extração dos dados tabulares.
   - **Cruzamento de Perfis:** Mapeamento entre o perfil do cliente (Conservador, Moderado, Arrojado) e os investimentos mais adequados (ex.: Poupança, CDBs, Fundos, Ações).
3. **Geração das Recomendações:**
   - Criação de mensagens personalizadas contendo o nome do cliente, saldo atual e sugestões de investimentos alinhadas ao seu perfil de risco.
## 🛠️ Tecnologias Utilizadas
- **Python 3:** Linguagem base para o script de automação RPA.
- **BeautifulSoup4:** Web scraping para extração de dados tabulares em HTML.
- **Requests:** Envio de requisições HTTP REST/JSON.
- **n8n:** Orquestração do workflow e automação de processos.
- **Git & GitHub:** Versionamento de código e documentação.
## 💡 Desafios Superados e Aprendizados
- Compreensão prática de arquitetura de redes entre ambientes locais (`localhost`) e serviços em nuvem.
- Integração de sistemas heterogêneos via Webhooks e consumo de APIs REST.
- Manipulação e tratamento de arquivos tabulares (CSV) consumidos externamente via requisição HTTP.
