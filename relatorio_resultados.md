# Relatório de Resultados — Teste de Usuário Final

> ⚠️ **Dados simulados.** Os valores deste relatório e dos arquivos em `dados/` são
> **fictícios**, criados para demonstrar o preenchimento da planilha, o cálculo das métricas
> e a análise. Eles não vêm de uma sessão real com participantes.

## 1. Identificação

| Item | Valor |
|---|---|
| Tipo de dados | Simulados (exemplo) |
| Número de participantes | 5 (P1 a P5) |
| Navegador | Google Chrome, janela anônima |
| Tarefas | T1 a T7 (ver `plano_de_teste.md`) |

## 2. Resultados quantitativos

Saída de `python3 analisar_resultados.py`:

```text
== Observações ==
Participante   Tempo (s)  Carrinho   Ajuda
P1                   138         S       N
P2                   212         S       N
P3                   117         S       N
P4                   288         S       S
P5                   157         S       N

Taxa de sucesso (carrinho sem ajuda): 4/5 = 80% -> meta 90%: NÃO ATINGIDA
Tempo médio: 182 s (3.0 min) -> meta 240 s: ATINGIDA

== SUS ==
P1              80.0  Bom
P2              57.5  Ruim / marginal
P3              95.0  Excelente
P4              37.5  Inaceitável
P5              75.0  Bom
Média SUS: 69.0 (Aceitável)
```

| Métrica | Resultado | Meta | Atingiu? |
|---|---|---|---|
| Taxa de sucesso (carrinho sem ajuda) | 80% (4/5) | ≥ 90% | ❌ Não |
| Tempo médio total | 182 s (3,0 min) | ≤ 240 s | ✅ Sim |
| Total de erros | 17 | — | — |
| Média SUS | 69,0 (Aceitável) | ≥ 68 | ✅ Sim (no limite) |

### Tempo e erros por tarefa

| Tarefa | Tempo médio (s) | Erros | Taxa de sucesso |
|---|---|---|---|
| T1 — Acessar site | 7,0 | 0 | 100% |
| T2 — Buscar produto | 16,2 | 1 | 100% |
| T3 — Aplicar filtros | **78,0** | **11** | **80%** |
| T4 — Abrir detalhes | 23,2 | 1 | 100% |
| T5 — Adicionar ao carrinho | 17,8 | 1 | 100% |
| T6 — Simular compra | 33,0 | 1 | 100% |
| T7 — Retornar à tela inicial | 7,2 | 2 | 100% |

A tarefa T3 (filtros) concentrou **65% dos erros** (11 de 17) e **43% do tempo médio** total.

## 3. Problemas de usabilidade encontrados

| # | Tarefa | Descrição do problema | Participantes afetados | Severidade |
|---|---|---|---|---|
| 1 | T3 | O filtro de entrega **Full** fica na barra lateral, longe da área onde os usuários procuraram primeiro (topo da página). | P1, P4, P5 | Alta |
| 2 | T3 | Os usuários não encontraram uma opção clara para **ordenar pelos melhores avaliados** no menu de ordenação. | P2, P4 | Alta |
| 3 | T3 | Depois de aplicar um filtro, a ordenação escolhida voltou ao padrão sem que o usuário percebesse. | P5 | Média |
| 4 | T5 | Os botões **Comprar agora** e **Adicionar ao carrinho** ficam lado a lado e geraram clique errado. | P2 | Média |
| 5 | T4 | Anúncios patrocinados se parecem com os resultados comuns e foram abertos por engano. | P4 | Baixa |
| 6 | T6 | Ao chegar no checkout, o usuário ficou inseguro se seria cobrado sem confirmar. | P4 | Baixa |
| 7 | T7 | Alguns usuários voltaram pelo botão do navegador em vez de usar o logotipo. | P2, P4 | Baixa |

## 4. Pontos positivos observados

- Busca rápida e eficiente: todos concluíram T2 em menos de 25 s.
- Adicionar ao carrinho (T5) foi concluído por todos, com apenas 1 erro.
- Página de detalhes com avaliações visíveis facilitou a comparação (P3 comparou abrindo abas).

## 5. Recomendações de melhoria

1. Dar mais destaque ao filtro **Full**, por exemplo como um chip de filtro rápido acima dos resultados.
2. Incluir a opção **"Melhores avaliados"** no menu de ordenação, ou deixar mais claro como filtrar por avaliação.
3. Manter a ordenação escolhida ao aplicar novos filtros e mostrar os filtros ativos em destaque.
4. Diferenciar visualmente "Comprar agora" de "Adicionar ao carrinho".
5. Identificar melhor os anúncios patrocinados.
6. No checkout, informar claramente que nada será cobrado antes da confirmação final.

## 6. Conclusão

Com os dados simulados, o teste **não atingiu** o critério principal de sucesso: 80% dos
usuários adicionaram o produto ao carrinho sem ajuda, abaixo da meta de 90%. O critério de
**tempo foi atingido** (média de 3,0 min, abaixo de 4 min) e a satisfação ficou **no limite do
aceitável** (SUS 69,0). O principal gargalo é a **etapa de filtros e ordenação (T3)**. Melhorar
a localização do filtro Full e a ordenação por avaliação deve ter o maior impacto na
usabilidade do fluxo.
