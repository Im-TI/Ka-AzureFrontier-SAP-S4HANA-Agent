# Ka-SAP-Copilot-Agent
Agente de IA criado para o Build Your First Copilot Challenge (Foundry Edition), projetado para responder dúvidas técnicas sobre migração do SAP ECC para o S/4HANA utilizando Azure AI Foundry
Perfeito, Kassia 🌟! Com os prints e o documento que você anexou, agora consigo montar uma versão final do seu **README.md** com os **passo a passo completos**, os **prints organizados**, e aquele toque leve e profissional que você pediu. Aqui está o modelo pronto para colar no seu repositório GitHub:

---

# 🚀 Ka-SAP Copiloto Agente

Projeto criado para o **Azure Frontier Girls – Build Your First Copilot Challenge (Foundry Edition)**  
Autora: **Kassia** — Especialista em Projetos SAP com superpoderes cognitivos ⚡

---

## 🧠 Sobre o agente

O **Ka-SAP Copiloto** é um agente inteligente que atua como suporte técnico para projetos SAP, especialmente voltado para **migração de SAP ECC para S/4HANA**. Ele consulta documentos técnicos armazenados no Azure Blob Storage e responde perguntas com base em conteúdo real dos PDFs, DOCX e HTMLs indexados.

💬 Ele entende perguntas como:
- "Quais são os recursos do SAP S/4HANA 2025?"
- "O que mudou no Cash Management?"
- "Tem guia de Central Finance?"

---

## 🛠️ Tecnologias Utilizadas

- Azure Cognitive Search  
- Azure Blob Storage  
- AI Foundry Agent Framework  
- PowerShell + REST API  
- GitHub (com README e prints obrigatórios)

---

## 📁 Estrutura do Projeto

| Componente | Descrição |
|------------|-----------|
| `sap-s4hana` | Índice de busca com os documentos técnicos |
| `saps4hanna-indexador` | Indexador que processa os arquivos do Blob |
| `saps4hanna-processed-source` | Fonte de dados conectada ao contêiner |
| `fileNameSuggester` | Suggester para autocomplete com nomes de arquivos |

---

## 📸 Passo a Passo com Prints

### 1. Criação da Conta de Armazenamento
- Tipo: LRS (Localmente Redundante) — menor custo e atende ao projeto.
- ![Print 1 – Conta de Armazenamento](./prints/01-conta-armazenamento.png)

### 2. Criação do Serviço de Pesquisa
- Azure AI Search configurado com boas práticas de governança (marcas aplicadas).
- ![Print 2 – Serviço de Pesquisa](./prints/02-servico-pesquisa.png)

### 3. Criação do Índice `sap-s4hana`
- Campos: `id`, `metadata_storage_name`, `metadata_storage_path`, `content`
- Configuração correta: `content` apenas *searchable* e *retrievable*
- ![Print 3 – Índice criado](./prints/03-indice-criado.png)

### 4. Criação da Fonte de Dados
- Conectada ao contêiner `saps4hanna-processed-source`
- ![Print 4 – Fonte de Dados](./prints/04-fonte-dados.png)

### 5. Criação e Execução do Indexador
- Nome: `saps4hanna-indexador`
- Extensões indexadas: `.pdf, .docx, .html`
- Resultado: 9/9 documentos indexados com sucesso 🎯
- ![Print 5 – Indexador criado](./prints/05-indexador-criado.png)
- ![Print 6 – Execução com sucesso](./prints/06-indexador-sucesso.png)

### 6. Teste via PowerShell
- Consulta geral:
  ```powershell
  Invoke-RestMethod `
    -Method Get `
    -Uri "https://agente-ka-sap-s4hana.search.windows.net/indexes/sap-s4hana/docs?search=*&$count=true&api-version=2023-07-01-Preview" `
    -Headers @{ "api-key" = "SUA_API_KEY" }
  ```
- Resultado: `@odata.count = 9`
- ![Print 7 – Resultado PowerShell](./prints/07-powershell-consulta.png)

### 7. Consulta específica: “Cash”
- Retorna documento de Cash Management
- ![Print 8 – Consulta específica](./prints/08-consulta-cash.png)

### 8. Autocomplete com Suggester
- Nome: `fileNameSuggester`
- Campo: `metadata_storage_name`
- Teste com `/docs/suggest?search=SAP`
- ![Print 9 – Suggester configurado](./prints/09-suggester-config.png)
- ![Print 10 – Resultado autocomplete](./prints/10-autocomplete.png)

---

## 🤖 Ação Funcional do Agente

- O agente responde perguntas sobre SAP S/4HANA usando os documentos indexados.
- Autocomplete sugere nomes de arquivos.
- Busca semântica melhora a relevância dos resultados.
- ![Print 11 – Resposta do agente](./prints/11-agente-resposta.png)

---

## 📚 Referências

- [AI Foundry](https://aka.ms/aifoundry)  
- [Microsoft Agent Framework](https://learn.microsoft.com/en-us/azure/ai-services/)  
- [Power Automate](https://learn.microsoft.com/en-us/power-automate/)  
- [Azure Cognitive Search](https://learn.microsoft.com/en-us/azure/search/)  




## 🧍‍♀️ Avatar 

- Personagem “PROJETOS SAP + AI Support” com óculos, earbuds e camisa laranja.
- ![Print 12 – Avatar Kassia](./prints/12-avatar-kassia.png)

---
<img width="768" height="1344" alt="Avatar Projeto SAP - Ka" src="https://github.com/user-attachments/assets/47870874-9a3f-4860-b6e8-8472fd7334a7" />

## ✅ Status Final

- Índice criado e populado  
- Indexador executado com sucesso  
- Autocomplete funcionando  
- README documentado com prints  
- Pronta para o voucher AZ-900 😎
