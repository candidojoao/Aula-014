# Aula 014 — Teste de Usuário Final (Usabilidade)

Atividade da Semana 14: teste de usuário final do fluxo de **busca, comparação e simulação de
compra** no site do Mercado Livre, aplicando conceitos de IHC e testes de usabilidade.

## Estrutura do repositório

| Arquivo | Conteúdo |
|---|---|
| [`plano_de_teste.md`](plano_de_teste.md) | Plano do teste: objetivo, cenário, tarefas, métricas, critérios de sucesso, papéis e roteiro de aplicação. |
| [`planilha_observacao.md`](planilha_observacao.md) | Planilha de observação por participante (tempo, sucesso, erros, observações). |
| [`questionario_sus.md`](questionario_sus.md) | Questionário SUS (System Usability Scale) e forma de cálculo. |
| [`dados/observacoes.csv`](dados/observacoes.csv) | Planilha digital para registrar as observações de cada tarefa. |
| [`dados/sus.csv`](dados/sus.csv) | Respostas do SUS por participante. |
| [`analisar_resultados.py`](analisar_resultados.py) | Calcula tempo médio, taxa de sucesso, erros e pontuação SUS, e compara com os critérios de sucesso. |
| [`relatorio_resultados.md`](relatorio_resultados.md) | Relatório final com resultados, problemas encontrados e recomendações. |

## Resumo dos resultados (dados simulados)

> Os dados em `dados/` e no relatório são **fictícios**, usados como exemplo.

| Métrica | Resultado | Meta |
|---|---|---|
| Taxa de sucesso | 80% | ≥ 90% ❌ |
| Tempo médio | 182 s | ≤ 240 s ✅ |
| SUS médio | 69,0 | ≥ 68 ✅ |

Principal problema: a etapa de filtros e ordenação (T3) concentrou 65% dos erros.
Detalhes em [`relatorio_resultados.md`](relatorio_resultados.md).

## Como aplicar

1. Formar duplas: um colega é o **usuário final** e o outro é o **avaliador**. O professor é o **instrutor**.
2. O avaliador lê o cenário do [`plano_de_teste.md`](plano_de_teste.md) e cronometra cada tarefa.
3. Durante a execução, o avaliador registra tempo, sucesso, erros e observações em `dados/observacoes.csv`.
4. Ao final, o usuário responde o questionário SUS e as notas são lançadas em `dados/sus.csv`.
5. Executar a análise:

   ```bash
   python3 analisar_resultados.py
   ```

6. Copiar a saída do script para o [`relatorio_resultados.md`](relatorio_resultados.md) e completar a análise qualitativa.

## Critérios de sucesso

- **90%** dos usuários devem conseguir adicionar o produto ao carrinho.
- **Tempo médio** para concluir o teste: **até 4 minutos (240 s)**.
