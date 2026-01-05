# Integrações Técnicas (Webhook + JSON)

## 1. Objetivo
Padronizar a integração entre:
**Formulário → Webhook → Make → IA → HubSpot → Logs**

## 2. Visão do fluxo
1) Um formulário envia dados do candidato (fictícios) para um **Webhook**.  
2) O **Make** recebe o JSON e valida campos.  
3) O Make chama a **IA** para triagem e recebe um **JSON de saída** padronizado.  
4) O Make grava/atualiza o registro no **HubSpot (Deals)**.  
5) O Make registra o resultado em **Logs** (planilha/DB).

## 3. JSON de Entrada (Candidato)
Arquivo: `schemas/candidato.input.json`

## 4. JSON de Saída (Triagem IA)
Arquivo: `schemas/triagem.output.json`

## 5. Mapeamento (Saída → HubSpot + Logs)
### HubSpot (Deal) — campos preenchidos
- candidate_id
- role_applied
- score_aderencia
- resumo_ia
- pontos_fortes_ia
- gaps_ia
- perguntas_sugeridas_ia
- recomendacao_etapa
- alertas_ia
- confidence_ia

### Logs — colunas recomendadas
- submitted_at
- candidate_id
- role_applied
- status_execucao (sucesso/erro)
- score_aderencia
- recomendacao_etapa
- alertas
