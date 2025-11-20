# LIA - LDantas Inteliggent Assistant

**Descrição:**  
LIA é o agente de atendimento da Imóveis LDantas, criado com Azure AI Foundry. Foca em orientar clientes sobre financiamento imobiliário, documentação, taxas (ITBI, emolumentos de cartório, seguros), e oferecer simulações básicas de financiamento.

**Objetivo do projeto:**  
- Disponibilizar um agente conversacional (LIA) no Azure AI Foundry.  
- Fornecer uma API simples de simulação de financiamento (Azure Function) que a LIA usa como *tool*.  
- Documentar o fluxo de atendimento, prints de execuções e orientações para deploy.

**Objetivo do agente:**  
- Orientação confiável e educativa  
- Atendimento 24h por dia
- Ajuda prática no processo de compra, venda ou aluguel
- Simulação de financiamento via integração com API

## Estrutura do repositório
- ** Link do Projeto no Azure AI Foundry
- https://laudi-mi7csea8-eastus2.services.ai.azure.com/api/projects/lia-ldantas


## Como rodar localmente (Azure Function)
1. Instalar as dependências (ver `azure-function/`).
2. `func start` (ou `python -m` conforme a função).
3. Testar a rota `/api/simulate` com `curl` ou Postman.

## Agent no Azure AI Foundry
- Endpoint do projeto Foundry:  
  `https://laudi-mi7csea8-eastus2.services.ai.azure.com/api/projects/lia-ldantas`  
- Modelo: **gpt-4o-mini** (serverless)   
- Agent definition: arquivo `agent-definition.json` (contém system prompt, exemplos e configurações).
- Ação integrada: Simulação de financiamento imobiliário
- Ferramenta: API externa via Azure Function

  
## Referências
- [Mais Mulheres Tech - (https://www.maismulheres.tech/courses/take/azure-frontier-girls/multimedia/70293690-build-your-first-copilot-challenge-foundry-edition-aula-e-explicacao-do-challenge)]
- [Generative AI for Beginners (Version 3) - A Course](https://microsoft.github.io/generative-ai-for-beginners/#/)
- [AI Agents for Begineers Repository](https://github.com/microsoft/ai-agents-for-beginners?WT.mc_id=academic-105485-koreyst)
- [MCP for Beginners Repository](https://github.com/microsoft/mcp-for-beginners?WT.mc_id=academic-105485-koreyst)
- [Discord do AI Foundry](https://aka.ms/foundry/discord)
- [Regioes dos modelos](https://learn.microsoft.com/en-us/azure/ai-foundry/agents/concepts/model-region-support?tabs=global-standard)

## Prints de respostas, fluxo e execução
[Azure Frontier Girls _ Nov 2025.pdf](https://github.com/user-attachments/files/23655133/Azure.Frontier.Girls._.Nov.2025.pdf)]

## Ação funcional implementada
**Simulação de financiamento** (`POST /api/simulate`)
POST https://<sua-function-url>/api/simulate

- Request JSON:
```json
{ "valor": 350000, "entrada": 70000, "anos": 30, "juros_ano": 0.10 }


