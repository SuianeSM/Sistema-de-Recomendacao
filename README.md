# Projeto — Teste A/B: Sistema de Recomendação
## Propósito

Validar se a introdução de um sistema aprimorado de recomendação melhora o desempenho do funil de conversão de novos usuários da União Europeia.

O foco é medir impacto real nas etapas:

**product_page → product_cart → purchase**

A expectativa do negócio era um aumento mínimo de 10% em cada etapa do funil, até 14 dias após o cadastro.

## Hipótese do experimento

H₀ (nula): Não há diferença estatisticamente significativa nas taxas de conversão entre os grupos A (controle) e B (novo sistema).

H₁ (alternativa): O grupo B apresenta taxas de conversão estatisticamente superiores ao grupo A em pelo menos uma etapa do funil.

## Contexto do teste

Teste: recommender_system_test

Grupos:

A — controle

B — novo sistema de recomendação

Período:

Início: 07/12/2020

Entrada de usuários: até 21/12/2020

Término: 01/01/2021

Audiência: 15% dos novos usuários da UE

Amostra esperada: ~6.000 usuários

## Dados utilizados

Usuários cadastrados no período do teste

Eventos comportamentais (visualização, carrinho, compra)

Participantes do experimento A/B

Calendário de campanhas de marketing (para identificar possíveis vieses)

Pré-processamento realizado:

Conversão correta de tipos de dados (datas e categorias)

Remoção de duplicatas

Validação de usuários em múltiplos grupos

Alinhamento temporal entre cadastro e eventos (janela de 14 dias)

## Limitações do experimento

Presença de campanhas de marketing ativas durante o teste, com potencial viés externo

Amostra menor do que o ideal para detectar efeitos pequenos

Análise focada apenas em métricas de funil, sem métricas intermediárias de engajamento

Não há evidência clara de que todos os usuários do grupo B foram igualmente expostos às recomendações

Esses fatores reduzem o poder estatístico do experimento.

## Análise realizada

Análise exploratória da distribuição de eventos por usuário e por dia

Construção do funil de conversão por grupo

Comparação das taxas de conversão entre A e B em cada etapa

Aplicação de teste Z para diferença de proporções

O teste Z foi utilizado por tratar-se da comparação de proporções binárias entre dois grupos independentes, com tamanho amostral suficiente para aproximação normal.

## Resultados

Product page → Cart

Diferença não estatisticamente significativa

p-value = 0,12

Cart → Purchase

Diferença não estatisticamente significativa

p-value = 0,53

Nenhuma etapa apresentou ganho estatístico ou atingiu o critério mínimo de +10%.

## Conclusões

O novo sistema de recomendação não apresentou impacto estatisticamente significativo no funil de conversão.

O comportamento dos usuários dos grupos A e B foi essencialmente equivalente em todas as etapas analisadas.

O experimento, da forma como foi conduzido, não fornece evidências suficientes para justificar rollout em produção.

## Recomendações

❌ Não implementar o novo sistema neste momento

Investigar gargalos no checkout e não apenas na recomendação

Avaliar posição, timing e contexto das recomendações

Executar novos testes A/B com:

Maior poder estatístico

Segmentação por dispositivo ou perfil de usuário

Métricas de engajamento (cliques, tempo em página, scroll)
