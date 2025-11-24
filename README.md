🚀 Ka-SAP Copilot Agent
Agente de IA criado para o Build Your First Copilot Challenge (Foundry Edition), projetado para responder dúvidas técnicas sobre migração do SAP ECC para o S/4HANA utilizando Azure AI Foundry.

Autora: Kassia Regina Camargo Costacurta — Especialista em Projetos SAP ⚡

🧠 Sobre o agente
O Ka-SAP Copilot é um agente inteligente que atua como suporte técnico em projetos SAP, especialmente voltado para migração de SAP ECC para S/4HANA.

Ele consulta documentos técnicos armazenados no Azure Blob Storage e responde perguntas com base em conteúdo real dos arquivos indexados (PDF, DOCX e HTML).

💬 Exemplos de perguntas que ele entende:

"Quais são os recursos do SAP S/4HANA 2025?"

"O que mudou no Cash Management?"

"Existe guia de Central Finance?"

🛠️ Tecnologias Utilizadas
Azure Cognitive Search

Azure Blob Storage

AI Foundry Agent Framework

PowerShell + REST API

GitHub

📁 Estrutura do Projeto

<img width="550" height="162" alt="image" src="https://github.com/user-attachments/assets/4b03b49e-01a2-441d-b259-503af3e86f10" />

      Componente	                  Descrição
sap-s4hana      	            Índice de busca com os documentos técnicos
saps4hanna-indexador	        Indexador que processa os arquivos do Blob
saps4hanna-processed-source  	Fonte de dados conectada ao contêiner
fileNameSuggester  	          Autocomplete com nomes de arquivos

📸 Passo a Passo com Prints

Criação da Conta de Armazenamento Tipo: LRS (Localmente Redundante) — menor custo e atende ao projeto.

Criação do Serviço de Pesquisa Configurado com boas práticas de governança.

Criação do Índice sap-s4hana Campos: id, metadata_storage_name, metadata_storage_path, content

Fonte de Dados Conectada ao contêiner saps4hanna-processed-source.

Indexador Nome: saps4hanna-indexador Extensões: .pdf, .docx, .html Resultado: 9/9 documentos indexados com sucesso 🎯

Teste via PowerShell

powershell

Invoke-RestMethod `
  -Method Get `
  -Uri "https://agente-ka-sap-s4hana.search.windows.net/indexes/sap-s4hana/docs?search=*&$count=true&api-version=2023-07-01-Preview" `
  -Headers @{ "api-key" = "SUA_API_KEY" }

Resultado: @odata.count = 9

Consulta específica: “Cash” Retorna documento de Cash Management.

Autocomplete com Suggester Campo: metadata_storage_name

🤖 Funcionalidades do Agente
Responde perguntas sobre SAP S/4HANA usando documentos indexados.

Autocomplete sugere nomes de arquivos.

Busca semântica melhora relevância dos resultados.


📚 Referências
AI Foundry

Microsoft Agent Framework

Power Automate

Azure Cognitive Search

🧍‍♀️ Avatar
Personagem “Projetos SAP + AI Support” com óculos, earbuds e camisa laranja.

<img width="768" height="1344" alt="Avatar Projeto SAP - Ka" src="https://github.com/user-attachments/assets/47870874-9a3f-4860-b6e8-8472fd7334a7" />
- Pronta para o voucher AZ-900 😎
