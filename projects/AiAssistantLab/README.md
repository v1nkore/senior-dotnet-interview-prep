# AiAssistantLab — план практического вертикального среза

Статус: запланирован, реализация ещё не начата.

Цель — не собрать универсального автономного агента, а пройти полный жизненный цикл одной надёжной AI-функции в привычном .NET backend-стеке.

## Вертикальный срез

```text
documents
   ↓ ingestion + ACL + version
PostgreSQL + pgvector
   ↓ hybrid retrieval + reranking
.NET API → model provider → structured answer + citations
   ↓                         ↓
OpenTelemetry            eval dataset in CI
```

## Итерации

1. .NET API, provider abstraction и ответ по JSON Schema.
2. Ingestion, chunking, embeddings и поиск через PostgreSQL + `pgvector`.
3. Metadata, ACL, hybrid search, reranking и цитаты.
4. Read-only tool и отдельное действие с human approval.
5. Golden dataset, retrieval/answer evals и порог регрессии в CI.
6. Traces, token/cost metrics, fallback и защита от prompt injection.

## Definition of done

- один и тот же eval-набор сравнивает минимум две версии prompt или retrieval;
- чужой документ не попадает в context даже при специально составленном запросе;
- tool arguments валидируются, опасное действие не выполняется без подтверждения;
- повтор действия не создаёт второй внешний side effect;
- trace показывает retrieval, model и tool spans без секретов и полного чувствительного prompt;
- README содержит измеренные latency, качество и стоимость, а не только описание архитектуры.

Подробная программа: [`../../docs/applied-ai-track.md`](../../docs/applied-ai-track.md).
